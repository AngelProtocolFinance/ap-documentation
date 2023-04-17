# Managing The Members Of A Multisig

<figure>
    <img src="/assets/diagrams/multisigs-member-mgmnt.png"
         alt="Managing Multisig Members">
	<figcaption>Shows how AST multisig contract member can manage themselves without any central mediation. Here we see an example of removing a member from the AST multig's owners list.</figcaption>
</figure>

Managing internal affairs of an AST multisig is the same process as any other transaction. The only difference is really that the destination is set as the multisig contract itself. This sort of setup is used for many common tasks such as:
 
- Adding a new member (owner)
`addOwner(address owner)`

- Removing a member (owner)
`removeOwner(address owner)`

- Replacing an existing member (owner) with a new one. This is useful for when an existing member loses access to their wallet or has it compromised and needs to change to a new wallet.
`replaceOwner(address owner, address newOwner)`