# Payments API
The readme file for the payments api

## Charges
Returns a list of charges you’ve previously created.
The charges are returned in sorted order, with the most recent charges appearing first.

```
/charges/{account}
```

## Balance
Retrieves the current account balance.

```
/balance/{account}
```

## Refunds
When you create a new refund, you must specify a charge to create it on.

Creating a new refund will refund a charge that has previously been created but not yet refunded. Funds will be refunded to the credit or debit card that was originally charged. The fees you were originally charged are also refunded.

You can optionally refund only part of a charge. You can do so as many times as you wish until the entire charge has been refunded.

Once entirely refunded, a charge can't be refunded again. This method will throw an error when called on an already-refunded charge, or when trying to refund more money than is left on a charge.
