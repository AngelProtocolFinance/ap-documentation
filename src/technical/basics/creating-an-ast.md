# Creating An AST

<figure>
    <img src="/assets/diagrams/ast-creation.png"
         alt="Creation of an AST">
	<figcaption>Flow of events and summary of the contracts involved in the creation of an AST Endowment on the Accounts contract. This example sets up Endowment #2, with a single owner multisig that does not require explicit execution.</figcaption>
</figure>

Any user who wishes to do so may create an AST. To do so you must use the createEndowment function on the Accounts diamond contract facet “AccountsCreateEndowment”. This endpoint expects an extensive configuration message that lays out all of the settings and parameters for the new AST. We’ll cover the function itself and the logic the message arguments and what they are for. 

The `createEndowment` function payload on the Accounts contract facet `AccountsCreateEndowment` expects a single argument struct like so: 
```javascript
struct CreateEndowmentRequest {
        address owner;
        bool withdrawBeforeMaturity;
        uint256 maturityTime;
        string name;
        AngelCoreStruct.Categories categories;
        uint256 tier;
        AngelCoreStruct.EndowmentType endow_type;
        string logo;
        string image;
        address[] cw4_members;
        bool kycDonorsOnly;
        AngelCoreStruct.Threshold cw3Threshold;
        AngelCoreStruct.Duration cw3MaxVotingPeriod;
        address[] whitelistedBeneficiaries;
        address[] whitelistedContributors;
        uint256 splitMax;
        uint256 splitMin;
        uint256 splitDefault;
        AngelCoreStruct.EndowmentFee earningsFee;
        AngelCoreStruct.EndowmentFee withdrawFee;
        AngelCoreStruct.EndowmentFee depositFee;
        AngelCoreStruct.EndowmentFee aumFee;
        AngelCoreStruct.DaoSetup dao;
        bool createDao;
        uint256 proposalLink;
        AngelCoreStruct.SettingsController settingsController;
        uint256 parent;
        address[] maturityWhitelist;
        bool ignoreUserSplits;
        AngelCoreStruct.SplitDetails splitToLiquid;
    }
```

We’ll breakdown what each of these arguments is used for, grouped by their area of application, and also how different choices for these will impact the created AST in terms of functionality.