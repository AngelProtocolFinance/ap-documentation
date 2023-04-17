# Placing Withdraws

<figure>
    <img src="/assets/diagrams/withdraw.png"
         alt="Withdraw from an AST">
	<figcaption>Shows a liquid withdraw proposal and execution for an AST from it's AST multisig.</figcaption>
</figure>

> ⚠️ **NOTE:** All withdraws from an AST come out of the Liquid Balance of Tokens on Hand. Locked Withdraws are NOT allowed from ASTs until the maturity time has been reached, hence the name.

The shape of a withdraw message is as follows:
```javascript
function withdraw(
    uint256 curId,
    AngelCoreStruct.AccountType acctType,
    address curBeneficiary,
    address[] memory curTokenaddress,
    uint256[] memory curAmount
)
```

In order to perform a withdraw:
1. An endowment member creates a transaction on the endowment multisig using the submitTransaction endpoint, with the destination address as the Accounts contract, a value set as 0 and the calldata for withdraw with liquid option. 
2. Other endowment members sign the transaction on multisig identified by transaction id.
3. Once (n/2+1)[the default, unless changed] signers sign transaction, it can be executed. However, this will happen automatically if the `require_execution` is set to false in the multisig config.