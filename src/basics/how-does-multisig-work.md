# How Does a Multisig Work?

<figure>
    <img src="/assets/diagrams/multisigs-voting.png"
         alt="Basic overview of AST Multsig">
	<figcaption>Shows the various steps and players involved in using an AST multisig contract, from initial transaction submission, confirmations, to the final execution of the payload.</figcaption>
</figure>

All actions taking place with a multisig follow the same flow: 
1. Propose a transaction
2. Acheive a passing level threshold of confimations
3. Execute the proposed transaction to the destination contract

## Submitting a transaction
Everything starts with a multisig member submitting a transaction for consideration for execution by the other members of a multisig. The output of a successful submission would be the resulting transaciton ID.

> ⚠️ **NOTE:** Take care to record this returned Endowment ID! It will be important for all members to interact with and sign a transaction and to lookup the status of a transaction. 

This message and args would look something like:
```javascript
submitTransaction("A short title", "description of the proposed transaction", "0x..1003", 0, <withdraw msg as binary>)
```

## Confirming a transaction
In order to confirm a pending multisig transaction members of the multisig must confirm the transaction. Members have several options available to them with regards to exercising their voting powers on a multisig contract for which they must submit the following messages, each time passing the transaction ID along as the sole argument:

### Confirm a Transaciton (approval vote for execution)
`confirmTransaction(uint256 transactionId)`

### Revoke a confirmation (recind a confirmation previously submitted for a transaciton)
`revokeConfirmation(uint256 transactionId)`

Once a transaction has aquired enough confirmations to meet the passing threshold level set it is ready for the final step: Execution!

## Executing a passing transaction
The hard work of gathering consensous amongst multisig members for a proposed transaction has been carried out. Now the time has come to execute the transaciton. This requires a single submission, which can be subitted by any valid EOA wallet, and will pass so long as:
1. The threshold for a transaction has been met
2. The data payload is valid and does not cause downstream errors that would cause the transaction to fail.

The execution message is very simple and looks like this: 
`executeTransaction(uint256 transactionId)`
