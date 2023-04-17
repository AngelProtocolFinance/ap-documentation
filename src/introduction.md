# Introduction

Welcome! I am excited you’ve decided to learn more about the Angel Smart Treasury (AST) from Angel Protocol. This document aims to help new develpers to understand the functionality and power offered by Angel Protocol’s smart contract platform so that they can quickly start building on top of us to deliver new and innovative financial solutions. 

## ELI5: What is the purpose of an AST?
An AST provides you with the tools to fundraise, coordinate, and invest capital in a transparent and frictionless manner. ASTs connect donors and investors with non-profits, social enterprises and other changemakers around the world. It’s a customizable, powerful, web3 infrastructure available in minutes!

## Who should read this guide?
This guide was written primarily with developers and tech-savy users in mind. It will help if you come in with an understanding of how the Polygon blockchain (or a similar EVM-based blockchain such as  Ethereum) and Solidity smart contracts work. We’ll be diving deeper into the technical aspects of how to use the Angel Protocol smart contracts directly here. 

If you’re looking for a higher level overview of the Angel Protocol ecosystem you can check out that guide here [LINK]. We also provide a UI-focused guide for users that do not want or need to directly interact with the smart contracts and would prefer to use the provided web application for managing their AST. 

That said there’s a lot to learned in the coming pages that will help you better understand and use our platform. :) Stick with it and you might be surprised! 

## How to read this?
This guide is written to provide explainations and details, along with code snippets and contract interfaces that would be commonly encountered when using an AST. These scenarios cover things like:
    • Creating an AST
    • How to use your AST’s multisig
    • Depositing and withdrawing funds from an AST

**Coming soon!**

- Updating and modifying the configuration parameters of an AST
- Investing and redeeming funds to/from Angel Protocol Strategies

We’ve ordered the first sections to quickly orient users to the core logic and structures at play in the Angel Protocol contracts and Endowments that are important to understand first, we then dive into the AST creation process and the basics of using an AST multisig. With those foundations in place we build upon that, covering the various day-to-day scenarios that AST members can expect to encounter. These latter sections can be treated as a reference guide rather than something that needs to be read cover-to-cover.  

Each section will cover the overview of the setup, players and contracts involved, any important logic points or considerations. We’ll also look at relevent code snippets for the involved endpoints as well as any important structs as we go. 

## Typographical Conventions Used

### Code Snippets
```javascript
function testAllTheThings() {
    // some 1337 code here...
}
```

### Important Points
> ⚠️ **Heads Up:** Important points will called out like this!


## Diagram Symbols Used

| Symbol      | Description |
| ----------- | ----------- |
| ![Smart Contract](./assets/symbols/smart-contract.png "Smart Contract") | Represents a smart contract on-chain. The "name" of the contract will always appear first in bold, along with an Address.       |
| ![Multisig Transaction](./assets/symbols/multisig-tx.png "Multisig Transaction") | Represents a single multisig contract transaction. These transactions are dependent on confirmation thresholds being reached to be executed. |
| ![Interactive Endpoint](./assets/symbols/contract-endpoint.png "Interactive Endpoint") | Represents an interactive endpoint on a smart contract. Messages always point at the blue receptor and outward flowing arrows represent downstream actions. |
| ![EOA Wallet](./assets/symbols/eoa-wallet.png "EOA Wallet") | Represents an EVM EOA wallet. |
| ![Logic Checkpoint](./assets/symbols/checkpoint.png "Contract Logic Checkpoint") | Represents a critical decision step in the contract logic. |
| ![Tokens](./assets/symbols/tokens.png "Tokens") | This is money. 😄 It is used to represent the flow of tokens and resulting balances in a contract or wallet. |
