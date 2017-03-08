# Payments API
The readme file for the payments api.

### TODO LIST
- [ ] Create API
- [ ] Create authenication system
- [ ] Create mobile application

### Future features
- [ ] Add products
- [ ] Add customers

### Mappings for API requests
Create  -> POST
Read    -> GET
Update  -> PUT
Delete  -> DELETE

## Account
#### Create
Create Stripe account for the user. 
```
/accounts
```
#### Read
Retrieves the details of the account.

```
/accounts/{account}
```
#### Update
Updates an account by setting the values of the parameters passed. Any parameters not provided will be left unchanged.

```
/accounts/{account}
```
#### Delete
Delete Stripe accounts you manage.

Managed accounts created using test-mode keys can be deleted at any time. Managed accounts created using live-mode keys may only be deleted once all balances are zero.
```
/accounts/{account}
```

## Bank Account
#### Create
If the bank account's owner has no other external account in the bank account's currency, the new bank account will become the default for that currency. However, if the owner already has a bank account for that currency, the new account will only become the default if the default_for_currency parameter is set to true.
```
accounts/{account}/bank_accounts
```

## Charges
#### Create
Returns a list of charges you’ve previously created.
The charges are returned in sorted order, with the most recent charges appearing first.

```
/charges/{account}
```

## Balance
#### Read
Retrieves the current account balance.

```
/balance/{account}
```

## Refunds
#### Create
When you create a new refund, you must specify a charge to create it on.

Creating a new refund will refund a charge that has previously been created but not yet refunded. Funds will be refunded to the credit or debit card that was originally charged. The fees you were originally charged are also refunded.

You can optionally refund only part of a charge. You can do so as many times as you wish until the entire charge has been refunded.

Once entirely refunded, a charge can't be refunded again. This method will throw an error when called on an already-refunded charge, or when trying to refund more money than is left on a charge.

```
/refunds/{account}/{charge}
```
