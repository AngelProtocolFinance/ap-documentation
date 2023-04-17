# Accounts Contract (Diamond)
This diamond contract is where all of the core business logic that governs all ASTs lives. If you are unfamiliar with what a Diamond is please stop and read over the [EIP-2535 specification](https://eips.ethereum.org/EIPS/eip-2535) to get an understanding and then come back here. Don’t worry we’ll wait! :) Everything else beyond this point will make a lot more sense after that.

The Accounts contract is responsible for:
- Tracking all existing Endowment accounts in the Angel Protocol ecosystem, their current status, and their configuration settings
- Managing the internal ledger for all Endowment balances
- Correctly applying logic for inbound deposits and outbound withdraws
- Providing the infrastructure to allow Endowment owners to make investments and redemptions to/from any Angel Protocol Strategy vaults, whether those are on the same chain or a different chain entirely
- Allow Endowment owners the ability to update their Configuration settings and manage things like permissions and control over changing various parameters

The other important concepts to wrap your head around, before we dive deeper into the code, is the distinction between the different types of Endowments, as well as the internal, accounting setup for all Endowment balances. 
