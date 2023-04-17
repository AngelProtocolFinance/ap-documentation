# Taking Deposits/Contributions

<figure>
    <img src="/assets/diagrams/deposit.png"
         alt="Deposits into an AST">
	<figcaption>Basic logic is illustrated, showing the flow of funds from a donor/contributor that wishes to deposit some funds into an AST.</figcaption>
</figure>

This is accomplished with the send of a valid deposit message to the Accounts contract any wallet. We will assume there are no restrictions on the wallets that can interact with the deposit endpoints for the sake of this example. Valid deposit message are supposed to be an ERC20 that exists in the Registrar contract’s approved tokens list. It looks like this:
```javascript
function depositERC20(
    AccountMessages.DepositRequest memory curDetails,
    address curTokenaddress,
    uint256 curAmount
) external;
```

As you can see we would need to pass along the amount to deposit, the token address of the deposit token, and a `DepositRequest` struct. That struct is rather simple and provides the Accounts contract further information about splits the user desires and which Endowment ID to credit the deposit to. It looks like this:
```javascript
struct DepositRequest {
        uint256 id;
        uint256 lockedPercentage;
        uint256 liquidPercentage;
    }
```
