# Registrar Contract

This contract serves as THE source of truth for all other Angel Protocol contracts on a given blockchain. It holds a large number of values in its storage struct that most other contracts will query to get the correct values for their own operations. It is owned and controlled by the Angel Protocol Team’s Admin multisig contract. Only this multisig can modify this contracts values.

The full config struct of the Registrar contract (as returned from a query to the getConfig endpoint):
```javascript
struct Config {
    address owner; // AP TEAM MULTISIG
    address applicationsReview;
    address indexFundContract;
    address accountsContract;
    address treasury;
    address subdaoGovCode;
    address subdaoCw20TokenCode;
    address subdaoBondingTokenCode;
    address subdaoCw900Code;
    address subdaoDistributorCode;
    address subdaoEmitter;
    address donationMatchCode;
    address donationMatchCharitesContract;
    address donationMatchEmitter;
    AngelCoreStruct.SplitDetails splitToLiquid;
    address haloToken;
    address haloTokenLpContract;
    address govContract;
    address collectorAddr;
    uint256 collectorShare;
    address charitySharesContract;
    AngelCoreStruct.AcceptedTokens acceptedTokens;
    address fundraisingContract;
    AngelCoreStruct.RebalanceDetails rebalance;
    address swapsRouter;
    address multisigFactory;
    address multisigEmitter;
    address charityProposal;
    address lockedWithdrawal;
    address proxyAdmin;
    address usdcAddress;
    address wethAddress;
    address cw900lvAddress;
}
```

Aside from managing the various contract addresses and wallet variables, the Registrar is also responsible for the curation of approved “Strategies” (ie. What ASTs invest their funds into) and “Network Information” about other external chains that Angel Protocol has Strategy Vaults deployed on.
The last important thing the Registrar handles is the management of the protocol level “Fees” that can be setup and applied when Endowments take certain actions like withdrawing funds from the protocol or when a harvest of Strategy vaults takes place.

Overall, the Registrar contract is a critically important contract to be aware of as you’re reading and understanding the code. It’s everywhere, and yet it’s not a contract you will ever really need to interact with directly.