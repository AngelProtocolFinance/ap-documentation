# AST Multsigs

Multisig contracts are commonplace in web3. They allow groups of users (the owners or members as they are often referred to as) to do things like approve transactions of shared assets held by their multisig contract and in general allow for better security of funds and addresses replacing users when they lose access to or have their signing wallet compromised. There a many different implementations of multisig contracts, but they usually share core similarities.

## Multisig Transactions

A transaction must collect signatures of approval from the members of the multisig. Just like in the "real-world", where voter petitions to a governing body need to have some thousands of signatures before it can be read before parliament, so too must a multisig transaction collect certain a number of signatures from its owners. The number of signatures that is required for a proposed transaction to have before it can be executed on-chain is called the threshold.

Once a transaction has collected signatures above the threshold, it can be executed by any valid wallet address on-chain. Execution is not limited to the member addresses themselves, which is useful when it comes to other contracts or scripts being able to execute transactions. 

## Want to go deeper?

If you are interested in learning more about multisig contracts in depth we can recommend the following articles and resources for additional reading:
- <a href="https://www.coindesk.com/learn/what-is-a-multisig-wallet/" target="_blank">What Is a Multisig Wallet? (Coindesk)</a> is a beginner friendly overview of multisig contracts
- <a href="https://shivanisb10.medium.com/multisig-contracts-in-ethereum-ffd8a1a9a025" target="_blank">Multisig Contracts in Ethereum (Medium)</a> is a more advanced overview of multisig contracts in EMVs using Solidity with discussions around on-chain vs off-chain signing of transactions
