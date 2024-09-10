---
title: "PG List of APIs"
slug: "pg-list-of-apis"
excerpt: ""
hidden: true
createdAt: "Mon Dec 05 2022 17:15:42 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Dec 06 2022 12:15:21 GMT+0000 (Coordinated Universal Time)"
---
**Orders** 

| API                                        | Description                                                                                              |
| :----------------------------------------- | :------------------------------------------------------------------------------------------------------- |
| [Create Order](ref:createorder)            | Use this API to create orders with Cashfree from your backend and get the payment link.                  |
| [Order Pay](ref:orderpay)                  | Use this API when you have already created the orders and want Cashfree Payments to process the payment. |
| [Preauthorization](ref:preauthorization-1) | Use this API to capture or void a preauthorized payment.                                                 |
| [Get Order](ref:getorder)                  | Use this API to view all details of an order.                                                            |

**Authentication**

| API                                    | Description                                               |
| :------------------------------------- | :-------------------------------------------------------- |
| [Submit or Resend OTP](ref:otprequest) | Use the submit or resend OTP API to send OTP to Cashfree. |

**Payments** 

| API                                                  | Description                                                        |
| :--------------------------------------------------- | :----------------------------------------------------------------- |
| [Get Payments for an Order](ref:getpaymentsfororder) | Use this API to view all payment details for an order.             |
| [Get Payment by ID](ref:getpaymentbyid)              | Use this API to view payment details of an order for a payment ID. |

**Settlements** 

| API                                                 | Description                                                                                               |
| :-------------------------------------------------- | :-------------------------------------------------------------------------------------------------------- |
| [Get Settlements by Order ID](ref:getsettlements-1) | Use this API to view all the settlements of a particular order.                                           |
| [Get All Settlements](ref:post_settlements)         | Use this API to get all settlement details by specifying the settlement ID, settlement UTR or date range. |

**Payment Links** 

| API                                                         | Description                                                                                                                                     |
| :---------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------- |
| [Create Payment Link](ref:createpaymentlink)                | Use this API to create a new payment link. The created payment link url will be available in the API response parameter link_url.               |
| [Fetch Payment Link Details](ref:getpaymentlinkdetails)     | Use this API to view all details and status of a payment link.                                                                                  |
| [Get Orders for a Payment Link](ref:getpaymentlinkorders-1) | Use this API to view all order details for a payment link.                                                                                      |
| [Cancel Payment Link](ref:cancelpaymentlink-1)              | Use this API to cancel a payment link. No further payments can be done against a cancelled link. Only a link in ACTIVE status can be cancelled. |

**Token Vault** 

| API                                                               | Description                                                                                                         |
| :---------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------ |
| [Fetch All Saved Instruments](ref:fetchallsavedinstruments)       | Use this API to get all saved instruments for a customer ID.                                                        |
| [Fetch Single Saved Instrument](ref:fetchspecificsavedinstrument) | Use this API to get specific saved instrument for a customer id and instrument ID.                                  |
| [Delete Saved Instrument](ref:deletespecificsavedinstrument)      | Use this API to delete a saved instrument for a customer id and instrument ID.                                      |
| [Fetch cryptogram for saved instrument](ref:fetchcryptogram)      | Use this API to get the card network token, token expiry and cryptogram for a saved instrument using instrument ID. |

**Reconciliation** 

| API                                               | Description                                                                                              |
| :------------------------------------------------ | :------------------------------------------------------------------------------------------------------- |
| [Settlement Reconciliation](ref:settlement-recon) | Use this API to get settlement reconciliation details using Settlement ID, settlement UTR or date range. |
| [PG Reconciliation](ref:pg_recon)                 | Use this API to get the payment gateway reconciliation details with date range.                          |
