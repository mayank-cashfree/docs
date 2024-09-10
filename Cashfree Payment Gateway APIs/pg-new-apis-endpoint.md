---
title: "End Points"
slug: "pg-new-apis-endpoint"
excerpt: ""
hidden: false
createdAt: "Sat Jan 08 2022 07:26:03 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Jan 30 2024 09:05:12 GMT+0000 (Coordinated Universal Time)"
---
# Payment Gateway End Points

[block:parameters]
{
  "data": {
    "h-0": "Environment",
    "h-1": "Base URL",
    "0-0": "Test",
    "0-1": "<https://sandbox.cashfree.com/pg>",
    "1-0": "Production",
    "1-1": "<https://api.cashfree.com/pg>",
    "2-0": "Latest version",
    "2-1": "v4, 2023-08-01  \nThe previous versions were 2021-05-21, 2022-01-01, 2022-09-01"
  },
  "cols": 2,
  "rows": 3,
  "align": [
    "left",
    "left"
  ]
}
[/block]


***

# Authentication

All the APIs require authentication, except the /orders/sessions API, which does not require any authentication and can be safely done from the browser as well.

Click [here](doc:authentication-3) for detailed information on API Authentication for Merchants and Partners.

***

# Payment Gateway APIs

## Orders

| API                                      | Description                                                                                              |
| :--------------------------------------- | :------------------------------------------------------------------------------------------------------- |
| [Create Order](ref:pgcreateorder)        | Use this API to create orders with Cashfree from your backend and get the payment link.                  |
| [Order Pay](ref:pgpayorder)              | Use this API when you have already created the orders and want Cashfree Payments to process the payment. |
| [Preauthorization](ref:pgauthorizeorder) | Use this API to capture or void a preauthorized payment.                                                 |
| [Get Order](ref:pgfetchorder)            | Use this API to view all details of an order.                                                            |

***

## Authentication

| API                                    | Description                                               |
| :------------------------------------- | :-------------------------------------------------------- |
| [Submit or Resend OTP](ref:otprequest) | Use the submit or resend OTP API to send OTP to Cashfree. |

***

## Payments

| API                                                  | Description                                                        |
| :--------------------------------------------------- | :----------------------------------------------------------------- |
| [Get Payments for an Order](ref:getpaymentsfororder) | Use this API to view all payment details for an order.             |
| [Get Payment by ID](ref:pgorderfetchpayment)         | Use this API to view payment details of an order for a payment ID. |

***

## Settlements

| API                                                       | Description                                                                                               |
| :-------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------- |
| [Get Settlements by Order ID](ref:pgorderfetchsettlement) | Use this API to view all the settlements of a particular order.                                           |
| [Get All Settlements](ref:pgfetchsettlements)             | Use this API to get all settlement details by specifying the settlement ID, settlement UTR or date range. |

***

## Payment Links

| API                                                    | Description                                                                                                                                     |
| :----------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------- |
| [Create Payment Link](ref:pgcreatelink)                | Use this API to create a new payment link. The created payment link url will be available in the API response parameter link_url.               |
| [Fetch Payment Link Details](ref:pgfetchlink)          | Use this API to view all details and status of a payment link.                                                                                  |
| [Get Orders for a Payment Link](ref:pglinkfetchorders) | Use this API to view all order details for a payment link.                                                                                      |
| [Cancel Payment Link](ref:pgcancellink)                | Use this API to cancel a payment link. No further payments can be done against a cancelled link. Only a link in ACTIVE status can be cancelled. |

***

## Token Vault

| API                                                                               | Description                                                                                                         |
| :-------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------ |
| [Fetch All Saved Instruments](ref:pgcustomerfetchinstruments)                     | Use this API to get all saved instruments for a customer ID.                                                        |
| [Fetch Single Saved Instrument](ref:pgcustomerfetchinstrument)                    | Use this API to get specific saved instrument for a customer id and instrument ID.                                  |
| [Delete Saved Instrument](ref:pgcustomerdeleteinstrument)                         | Use this API to delete a saved instrument for a customer id and instrument ID.                                      |
| [Fetch Cryptogram for Saved Instrument](ref:pgcustomerinstrumentsfetchcryptogram) | Use this API to get the card network token, token expiry and cryptogram for a saved instrument using instrument ID. |

***

## Reconciliation

| API                                                     | Description                                                                                              |
| :------------------------------------------------------ | :------------------------------------------------------------------------------------------------------- |
| [Settlement Reconciliation](ref:pgsettlementfetchrecon) | Use this API to get settlement reconciliation details using Settlement ID, settlement UTR or date range. |
| [PG Reconciliation](ref:pgfetchrecon)                   | Use this API to get the payment gateway reconciliation details with date range.                          |
