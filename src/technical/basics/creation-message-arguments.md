# Creation Message Arguments

## Endowment Owner

`address owner;`
This field should usually be set as the message sender EOA, as it will only be used temporarily until the AST Multisig is created and set as the true owner. 

## Endowment Type

`AngelCoreStruct.EndowmentType endow_type;`
This field expects and EndowmentType enum:
```javascript
enum EndowmentType {
        Charity,
        Normal,
        None
    }
```

It should always be set as "Normal" for AST creation message. 

## Endowment Tier

`uint256 tier;`
This field should always be set as 0 for AST creation messages. This field is used exclusively by Charity endowments. 

## Maturity Time

```javascript
bool withdrawBeforeMaturity;
uint256 maturityTime;
```
These fields are responsible for controlling when the AST Endowment will mature at and whether or not withdraws are possible before this maturity date. Both of these fields can only be set at the time of instantiation. 

If `withdrawBeforeMaturity == true`, then funds will be be able to be withdrawn before the maturity date, if set to false, then funds are locked until maturity is set (if ever). 

The maturityTime field, if non-zero, sets the time that the Endowment will mature at. If `0` the endowment effectively has no maturity date (indefinite).

## Categories and UN SDGs

`AngelCoreStruct.Categories categories;`
This field expects a Categories struct which lays out the UN SDGs and General categories that apply to an Endowment:
```javascript
struct Categories {
    uint256[] sdgs;
    uint256[] general;
}
```

SDGs are used mostly with Charity endowments only, though they could be used by an AST if desired, though having at least 1 SDG set is not a requirement for them, unlike with Charity endowments. General categories is a open, flexible system thin which AST owners can set integer values on chain for internally defined categories. This General category might be useful for users that have many ASTs or those that have my sub-AST (child ASTs) that want to group them by internal classifiers.

## Basic Endowment Info Strings

```javascript
string name;
string logo;
string image;
```
These fields are simple, informational string vaules that will help identify your AST endowment on-chain and can be used by those who are not using suplemental database storages for AST information. 
- Name: The name of your AST
- Logo: A URL string that points to your AST’s logo image
- Image: A URL string that points to your AST’s banner/suplemental image

## KYC Required

`bool kycDonorsOnly;`
If set to true, the AST is stating its preference for only recieving funds from KYC’d donors/contibutors. This is something that would be read by and enforced from the frontend environment, as there’s currently no real way to do this on-chain today.

## MultiSig Initial Configs

```javascript
address[] cw4_members;
AngelCoreStruct.Threshold cw3Threshold;
AngelCoreStruct.Duration cw3MaxVotingPeriod;
```
The above argments control the starting vaules for the AST Endowment’s MultiSig.
- cw4_members: A list of EVM addresses that should be setup as the starting owners/members of the AST Endowment multisig
- cw3Threshold: This argument expects a Threshold struct which lays out the following: 
```javascript
struct Threshold {
    ThresholdEnum enumData;
    ThresholdData data;
}
```

`ThresholdEnum` struct specifies the type of threshold used:
```javascript
enum ThresholdEnum {
    AbsoluteCount,
    AbsolutePercentage,
    ThresholdQuorum
}
```

ThresholdData struct is where the relevent values for the above threshold type are passed. When not applicable, a 0 value can be passed:
```javascript
struct ThresholdData {
    uint256 weight;
    uint256 percentage;
    uint256 threshold;
    uint256 quorum;
}
```

## Whitelists 

```javascript
address[] whitelistedBeneficiaries;
address[] whitelistedContributors;
address[] maturityWhitelist;
```
These values setup the allow lists for what restrictions, if any, will exist for those wallets that will be beneficiaries of or contributors to the AST. If an empty array is passed it is assumed that there should be NO restrictions on that field (ie. Any wallet address will be allowed). 
The maturityWhitelist field is the set of addresses that can access the AST funds at the time of maturity. It is distinct from the other two whitelists here, which apply only while the AST is not yet mature. 

## Split Logic 

```javascript
uint256 splitMax;
uint256 splitMin;
uint256 splitDefault;
bool ignoreUserSplits;
AngelCoreStruct.SplitDetails splitToLiquid;
```
???

## Custom Fees

```javascript
AngelCoreStruct.EndowmentFee earningsFee;
AngelCoreStruct.EndowmentFee withdrawFee;
AngelCoreStruct.EndowmentFee depositFee;
AngelCoreStruct.EndowmentFee aumFee;
```
???

## Settings Controller

`AngelCoreStruct.SettingsController settingsController;`
This field expects a `SettingsController` struct which lays out on-chain enforced rules as to whom can make changes to which AST endowment fields and settings:
```javascript
struct SettingsController {
    SettingsPermission endowmentController;
    SettingsPermission strategies;
    SettingsPermission whitelistedBeneficiaries;
    SettingsPermission whitelistedContributors;
    SettingsPermission maturityWhitelist;
    SettingsPermission maturityTime;
    SettingsPermission profile;
    SettingsPermission earningsFee;
    SettingsPermission withdrawFee;
    SettingsPermission depositFee;
    SettingsPermission aumFee;
    SettingsPermission kycDonorsOnly;
    SettingsPermission name;
    SettingsPermission image;
    SettingsPermission logo;
    SettingsPermission categories;
    SettingsPermission splitToLiquid;
    SettingsPermission ignoreUserSplits;
}
```

As you can see from the struct shape and contents, the `SettingsController` struct is a set of fields which hold `SettingsPermissions` struct with have all the relevent permissions details encoded:
```javascript
struct SettingsPermission {
    bool ownerControlled;
    bool govControlled;
    bool modifiableAfterInit;
    Delegate delegate;
}
```

## Parent / Child Endowments

`uint256 parent;`
If you have an existing AST Endowment that will be the parent/owner of a sub-AST or child AST Endowment, this field is where that parent AST Endowment ID should be placed. The time of creation  is the only opportunity at the present time where this field can be set. If no parent is needed, as will be the case for most AST users, simply pass a 0 value here.
