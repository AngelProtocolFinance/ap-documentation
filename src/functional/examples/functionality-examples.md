# Functionality Examples

## Simple Multisig

The default setup for AST on creation is a multisig (i.e. Admin Wallet). This is the simplest form of an AST. At any time, the owners of ASTs can opt-in for tokenized governance with either an existing token or by creating a new token. At the moment of the opt-in, the owners can decide which parameters of the AST fall under the governance and which are still controlled by the native multi-sig.

![simple-multisig](../../assets/examples/simple-multisig.png "simple-multisig")

## Existing Token

When the owners of an AST decide to opt-in for DAO governance using an existing token, a governance contract is instantiated that allows token holders to vote on the parameters that have been chosen by the contract owner.

Eligible tokens are pre-approved by the AP DAO along with a designated AMM token pair contract address that is used to convert fees from the AST (generally denominated in stablecoins) into the token in use for distribution to stakers as rewards.

The owners of an AST can instantiate a Matching contract that contains a reserve of tokens that are distributed to contributors following a set of rules defined by the governance of the AST.

A Rewards contract can also be instantiated that enables using a reserve of tokens to increase staking rewards.

![existing-token](../../assets/examples/existing-token.png "existing-token")

## New Token Setup

### Fixed Supply

![new-token-fixed](../../assets/examples/new-token-fixed.png "new-token-fixed")


### Bonding Curve

![new-token-bonding](../../assets/examples/new-token-bonding.png "new-token-bonding")


## Simple Personal Endowment

![personal-endowment-1](../../assets/examples/personal-endowment-1.png "personal-endowment-1")
![personal-endowment-2](../../assets/examples/personal-endowment-2.png "personal-endowment-2")

## Charitable Estate Planning Trust

![charitable-estate-planning-trust-1](../../assets/examples/charitable-estate-planning-trust-1.png "charitable-estate-planning-trust-1")
![charitable-estate-planning-trust-2](../../assets/examples/charitable-estate-planning-trust-2.png "charitable-estate-planning-trust-2")

## Employee Pension Plan

![employee-pension-plan-1](../../assets/examples/employee-pension-plan-1.png "employee-pension-plan-1")
![employee-pension-plan-2](../../assets/examples/employee-pension-plan-2.png "employee-pension-plan-2")


## Social Impact Fund

![social-impact-fund-1](../../assets/examples/social-impact-fund-1.png "social-impact-fund-1")
![social-impact-fund-2](../../assets/examples/social-impact-fund-2.png "social-impact-fund-2")


## Lossless Impact Group

![lossless-impact-group-1](../../assets/examples/lossless-impact-group-1.png "lossless-impact-group-1")
![lossless-impact-group-2](../../assets/examples/lossless-impact-group-2.png "lossless-impact-group-2")

## Social Impact Collective

![social-impact-collective-1](../../assets/examples/social-impact-collective-1.png "social-impact-collective-1")
![social-impact-collective-2](../../assets/examples/social-impact-collective-2.png "social-impact-collective-2")

