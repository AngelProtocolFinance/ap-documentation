# Types of Endowments

Angel Protocol has two types of Endowments at the smart contract level: Charity Endowments & Normal Endowments. The internal representation for an EndowmentType in the contracts is an enum:
```javascript
enum EndowmentType {
    Charity,
    Normal,
    None
}
```

Charity Endowments are specialized Endowments reserved only for vetted and verified Non-Profit Organizations. These are outside the scope of this guide, but it is important to know they exist for when you see them mentioned throughout the logic in the smart contracts codebase. Normal Endowments are  ASTs. So when you see references to “Normal” Endowments in the codebase, just think AST and you will be okay. We will use AST throughout this guide to avoid any confusion. AST Endowments have far greater flexibility with regards to their configuration options and their management capabilities. They are the v2 of the Charity Endowments.
