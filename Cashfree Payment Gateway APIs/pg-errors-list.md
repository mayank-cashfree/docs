---
title: "Errors - Structure and List"
slug: "pg-errors-list"
excerpt: ""
hidden: false
createdAt: "Wed Sep 21 2022 08:48:56 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Thu Mar 02 2023 12:57:21 GMT+0000 (Coordinated Universal Time)"
---
# Error Structure

The Payment Gateway response in case of an error includes the following:

- **error_code** - Code associated with every error
- **error_description** - Description of the error
- **error_source** - Source of the error
- **error_reason** - Failure reason

**Sample error response**:

<pre><code>
{
	"auth_id": null,
	"authorization": null,
	"bank_reference": "306118259130",
	"cf_payment_id": 1636676360,
	"entity": "payment",
	"error_details": {
		"error_code": "TRANSACTION_DECLINED",
		"error_description": "transaction is rejected at the remitter bank end. Please reach out to issuer bank",
		"error_reason": "bank_rejected",
		"error_source": "bank"
		},
	"is_captured": false,
	"order_amount": 1.00,
	"order_id": "order_18482MSWq8prPMOW0jTeGsx0B1JmPC1",
	"payment_amount": 1.00,
	"payment_completion_time": "2023-03-02T18:24:51+05:30",
	"payment_currency": "INR",
	"payment_group": "upi",
	"payment_message": "01::REJECTED",
	"payment_method": {
		"upi": {
			"channel": "collect",
			"upi_id": "8XXXXXXXX2@upi"
			}
		},
	"payment_status": "FAILED",
	"payment_time": "2023-03-02T18:24:18+05:30"
}
</code></pre>

***

# List of Errors for Payments

Download the list of errors along with their explanation.

<a href="https://gocashassets.s3.ap-south-1.amazonaws.com/repostmancollection/Error+List.xlsx"  target="_blank" download>Payment Error List</a>

> 📘 Note:
> 
> Error details will be shown for every failed transaction in the payload of the following APIs and webhook: 
> 
> - [Get Payments for an Order](ref:getpaymentsfororder)
> - [Get Payment by ID](ref:getpaymentbyid)
> - [Payment Failed Webhook](doc:payment-webhooks#payment-failed-webhook)
