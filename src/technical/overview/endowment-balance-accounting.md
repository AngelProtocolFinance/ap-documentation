# Endowment Balance Accounting
Regardless of their Type, all Endowments recorded in the Accounts contract have a Locked Account and an Liquid Account balance. Internally in the contracts this is represented by an enum AccountType:
```javascript
enum AccountType {
    Locked,
    Liquid,
    None
}
```

The Locked portion represents the balance that is...well locked and cannot be withdrawn. It is helpful to think of this as the “endowment” portion of your account, the part that is set aside to be invested and grow un-distributed. The Liquid portion can be thought of like a current (or checking) bank account where there are little to no restriction on how much, to whom, or when money can be taken out of it.
