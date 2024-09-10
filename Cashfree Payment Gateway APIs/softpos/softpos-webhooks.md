---
title: "softPOS Webhooks"
slug: "softpos-webhooks"
excerpt: "Learn in detail about softPOS webhooks."
hidden: false
createdAt: "Fri Nov 03 2023 13:39:31 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Mon Apr 29 2024 08:59:37 GMT+0000 (Coordinated Universal Time)"
---
Webhooks are server callbacks to your server from Cashfree Payments. Webhooks are event-based and are sent when specific events related to the transaction happen.

Cashfree Payments sends the following webhooks for softPOS:

- [Payment Success](ref:softpos-webhooks#payment-success-webhook-version-2022-09-01)
- [Payment Failed](ref:softpos-webhooks#payment-failed-webhook-version-2022-09-01)
- [User Dropped](ref:softpos-webhooks#user-dropped-webhook-version-2022-09-01)
- [Refunds](ref:softpos-webhooks#refund-webhook-version-2022-09-01)
- [Auto Refund](ref:softpos-webhooks#auto-refund-webhook-version-2022-09-01)
- [Disputes](ref:softpos-webhooks#dispute-webhooks-version-2022-09-01)
- [Settlements](https://docs.cashfree.com/docs/settlements-webhook)
- [Terminal](https://docs.cashfree.com/reference/softpos-webhooks#terminal-status-update-webhook-version-2022-09-01) 

***

# Payment Success Webhook Version: (2022-09-01)

The new payment success webhook notifies you about the payment, and gives you comprehensive information about successful payments. A notification is sent to your backend from Cashfree Payments when payments are successful. These notifications are useful in cases when the internet connection is unstable or slow while the payment is being processed. This will allow you to reconcile all the successful orders at your end. Notifications will be sent to **notifyUrl** which is a part of the request parameter specified while creating an order request as well as endpoints configured on the merchant dashboard.

### Sample Payload

<pre><code> {  
  "data": {
        "order": {
            "order_id": "order_OFR_2",
            "order_amount": 2,
            "order_currency": "INR",
            "order_tags": null
        },
        "payment": {
            "cf_payment_id": 1453002795,
            "payment_status": "SUCCESS",
            "payment_amount": 1,
            "payment_currency": "INR",
            "payment_message": "00::Transaction success",
            "payment_time": "2022-12-15T12:20:29+05:30",
            "bank_reference": "234928698581",
            "auth_id": null,
            "payment_method": {
                "upi": {
                    "channel": null,
                    "upi_id": "9611199227@paytm"
                }
            },
            "payment_group": "upi"
        },
        "customer_details": {
            "customer_name": null,
            "customer_id": "7112AAA812234",
            "customer_email": "[miglaniyogesh7@gmail.com]()",
            "customer_phone": "9908734801"
        },
        "payment_gateway_details": {
            "gateway_name": "CASHFREE",
            "gateway_order_id": "1580762800",
            "gateway_payment_id": "1453002795",
            "gateway_status_code": null
        },
        "payment_offers": [  
            {  
                "offer_id": "0f05e1d0-fbf8-4c9c-a1f0-814c7b2abdba",  
                "offer_type": "DISCOUNT",  
                "offer_meta": {  
                    "offer_title": "50% off on UPI",  
                    "offer_description": "50% off for testing",  
                    "offer_code": "UPI50",  
                    "offer_start_time": "2022-11-09T06:23:25.972Z",  
                    "offer_end_time": "2023-02-27T18:30:00Z"  
                },  
                "offer_redemption": {  
                    "redemption_status": "SUCCESS",  
                    "discount_amount": 1,  
                    "cashback_amount": 0  
                }  
            }  
        ],
        "terminal_details": {
        "cf_terminal_id": 989876,
        "terminal_phone": "9773769999"
    }
    },
    "event_time": "2023-01-03T11:16:10+05:30",
    "type": "PAYMENT_SUCCESS_WEBHOOK"
}

</code></pre>

***

# Payment Failed Webhook Version: (2022-09-01)

The payment failed webhook notifies you when transactions fail and we receive a failed response from the bank.

<pre><code>{  
    "data": {
    "order": {
        "order_id": "CFPay_g47u3888d0k0_tblfm766qc",
        "order_amount": 1.8,
        "order_currency": "INR",
        "order_tags": {
            "cf_link_id": "13746255"
        }
    },
    "payment": {
        "cf_payment_id": 1504280029,
        "payment_status": "FAILED",
        "payment_amount": 1.8,
        "payment_currency": "INR",
        "payment_message": "AMOUNT SHOULD BE WITHIN RANGE BETWEEN 20.00 TO 500000.00.",
        "payment_time": "2023-01-06T20:00:11+05:30",
        "bank_reference": "NA",
        "auth_id": "null",
        "payment_method": {
            "netbanking": {
                "channel": null,
                "netbanking_bank_code": "3054",
                "netbanking_bank_name": "UCO Bank"
            }
        },
        "payment_group": "net_banking"
    },
    "customer_details": {
        "customer_name": null,
        "customer_id": null,
        "customer_email": null,
        "customer_phone": "9611199227"
    },
    "error_details": {
        "error_code": "GATEWAY_ERROR",
        "error_description": "AMOUNT SHOULD BE WITHIN RANGE BETWEEN 20.00 TO 500000.00. for this bank",
        "error_reason": "invalid_amount",
        "error_source": "cashfree"
    },
    "payment_gateway_details": {
        "gateway_name": "CASHFREE",
        "gateway_order_id": "1634766330",
        "gateway_payment_id": "1504280029",
        "gateway_status_code": null
    },
    "payment_offers": null,
    "terminal_details": {
        "cf_terminal_id": 989876,
        "terminal_phone": "9773769999"
    }
},
"event_time": "2023-01-06T20:00:12+05:30",
"type": "PAYMENT_FAILED_WEBHOOK"
}
</code></pre>

***

# User Dropped Webhook Version: (2022-09-01)

The User Dropped Webhook notifies you when customers drop out of the payment flow without completing the transaction. It will help you understand if customers attempted to pay or not.

Some common scenarios where the transaction will be marked as USER_DROPPED are:

- Android UPI Intent Payments - when a user clicks on the back button in the UPI app without making any payment attempt.
- Card Payments - when a user drops out of the payment flow by closing the OTP verification page.
- UPI Collect Transactions - when a user does not enter the UPI PIN and closes the transaction screen

<pre><code>{  
    "data": {
        "order": {
            "order_id": "testspos83",
            "order_amount": 1.00,
            "order_currency": "INR",
            "order_tags": null
        },
        "payment": {
            "cf_payment_id": 2150264295,
            "payment_status": "USER_DROPPED",
            "payment_amount": 1.00,
            "payment_currency": "INR",
            "payment_message": null,
            "payment_time": "2023-11-03T12:37:32+05:30",
            "bank_reference": null,
            "auth_id": null,
            "payment_method": {
                "upi": {
                    "channel": null,
                    "upi_id": "testsuccess@gocash"
                }
            },
            "payment_group": "upi"
        },
        "customer_details": {
            "customer_name": "johndoe",
            "customer_id": "9112",
            "customer_email": "[johndoe@cashfree.com]()",
            "customer_phone": "9876543210"
        },
        "payment_gateway_details": {
            "gateway_name": null,
            "gateway_order_id": null,
            "gateway_payment_id": null,
            "gateway_status_code": null,
            "gateway_settlement": null
        },
        "payment_offers": null,
        "terminal_details": {
            "cf_terminal_id": 20532321,
            "terminal_phone": "9876543210"
        }
    },
    "event_time": "2023-11-03T12:37:44+05:30",
    "type": "PAYMENT_USER_DROPPED_WEBHOOK"
}
</code></pre>

***

# Refund Webhook Version: (2022-09-01)

Refund webhooks can be configured to receive automated notifications for refunds when either they are successfully processed or are cancelled. Merchants can build their own downstream systems like auto-updating their refund status, and sending a communication to customers by consuming refund webhooks.

The webhook notification will be sent on all the URLs added and enabled under the refund webhook. Merchants can add new URLs and enable or disable existing URLs for refund webhook at any point in time and it will be reflected instantaneously.

### Sample Payload

<pre><code>
{
 "data": {
    "refund": {
        "cf_refund_id": 11325632,
        "cf_payment_id": 789727431,
        "refund_id": "refund_sampleorder0413",
        "order_id": "sampleorder0413",
        "refund_amount": 2.00,
        "refund_currency": "INR",
        "entity": "Refund",
        "refund_type": "MERCHANT_INITIATED",
        "refund_arn": "205907014017",
        "refund_status": "SUCCESS",
        "status_description": "Refund processed successfully",
        "created_at": "2022-02-28T12:54:25+05:30",
        "processed_at": "2022-02-28T13:04:27+05:30",
        "refund_charge": 0,
        "refund_note": "Test",
        "refund_splits": [  
            {  
                "merchantVendorId": "sampleID12345",  
                "amount": 1,  
                "percentage": null  
            },  
            {  
                "merchantVendorId": "otherVendor",  
                "amount": 1,  
                "percentage": null  
            }  
        ],
        "metadata": null,
        "refund_mode": "STANDARD",
        "terminal_details": {
            "cf_terminal_id": 911876,
            "terminal_phone": "9876543210"
        }
    }
},
"event_time": "2022-02-28T13:04:28+05:30",
"type": "REFUND_STATUS_WEBHOOK"
}
</code></pre>

### Payload Field Description

| Field              | Description                                                                 | Example                       |
| :----------------- | :-------------------------------------------------------------------------- | :---------------------------- |
| cf_refund_id       | Cashfree Payments ID for a refund.                                          | 11325632                      |
| cf_payment_id      | Cashfree Payments ID of the payment for which refund is initiated.          | 789727431                     |
| cf_terminal_id     | Cashfree Payments Terminal ID of the payment for which refund is initiated. | 21345                         |
| terminal_phone     | The phone number of the corresponding terminal.                             | 9876543212                    |
| refund_id          | Merchant’s refund ID of the refund                                          | refund_sampleorder0413        |
| order_id           | Merchant’s order Id of the order for which refund is initiated.             | sampleorder0413               |
| refund_amount      | Amount that was refunded                                                    | 2.00                          |
| refund_currency    | Currency of the refund amount.                                              | INR                           |
| entity             | Type of object (refund always)                                              | Refund                        |
| refund_type        | Type of refund (for webhook it will always be MERCHANT_INITIATED)           | MERCHANT_INITIATED            |
| refund_arn         | The bank reference number for refund                                        | 205907014017                  |
| refund_status      | Status of the refund (either SUCCESS or CANCELLED in refund webhook)        | SUCCESS                       |
| status_description | Description of refund status                                                | Refund processed successfully |
| created_at         | Time of refund creation                                                     | 2022-02-28T12:54:25+05:30     |
| processed_at       | Time when refund was processed successfully                                 | 2022-02-28T13:04:27+05:30     |
| refund_charge      | Charges in INR for processing refund                                        | 0                             |
| refund_note        | Note added by merchant for the refund                                       | Cancelled Order               |
| refund_splits      | Refund split details                                                        | \[]                           |
| metadata           | Additional refund metadata                                                  | null                          |
| refund_mode        | Method or speed of processing refund (INSTANT or STANDARD)                  | STANDARD                      |
| event_time         | Time at which refund webhook was initiated.                                 | 2022-02-28T13:04:28+05:30     |
| type               | Type of webhook. REFUND_STATUS_WEBHOOK always                               | REFUND_STATUS_WEBHOOK         |

***

# Auto Refund Webhook Version: (2022-09-01)

Auto-refund webhooks can be configured to receive automated notifications when auto-refunds are initiated, processed and delayed. Auto-refunds are refunds triggered automatically for unsuccessful payments, disputes, duplicate payments; or instances where payments are received directly to your VPA, regardless of whether an order has been generated.

Webhook notifications are sent to every URL added and enabled under **Auto-refund Webhooks**. Merchants can add new URLs and enable or disable existing ones for auto-refund webhooks at any point in time. The changes are reflected instantaneously. 

### Sample Payload

```Text Auto-Refund Webhook Sample Payload
{
    "data": {
        "auto_refund": {
            "event": "AUTO-REFUND",
            "cf_refund_id": 1243460973,
            "cf_payment_id": "2148333968",
            "bank_reference": "234928698581",
            "order_id": "order_1944392Tpba8y2fHcHVx0SwREojp51Jgr",
            "refund_amount": 39,
            "refund_currency": "INR",
            "refund_type": "PAYMENT_AUTO_REFUND",
            "refund_arn": "205907014017",
            "refund_status": "SUCCESS",
            "status_description": "Auto-Refund processed successfully",
            "refund_reason": "Multiple payments were performed against same order.",
            "created_at": "2023-08-11T14:08:28+05:30",
            "processed_at": null,
            "refund_charge": 0,
            "refund_splits": null,
            "metadata": null
        },
        "terminal_details": {
            "cf_terminal_id": 989876,
            "terminal_phone": "9773769999"
        }
    },
    "event_time": "2023-08-11T14:10:21+05:30",
    "type": "AUTO_REFUND_STATUS_WEBHOOK"
}
```

Find the description for each field of the payload below:

[block:parameters]
{
  "data": {
    "h-0": "Field",
    "h-1": "Description",
    "h-2": "Example",
    "0-0": "cf_refund_id",
    "0-1": "It represents the ID created by Cashfree Payments to identify the refund.",
    "0-2": "1243460973",
    "1-0": "cf_payment_id",
    "1-1": "It represents the ID created by Cashfree Payments to identify the payment for the initiated refund.",
    "1-2": "2148333968",
    "2-0": "cf_terminal_id",
    "2-1": "Cashfree Payments Terminal ID of the payment for which refund is initiated. ",
    "2-2": "21345",
    "3-0": "terminal_phone",
    "3-1": "The phone number of the corresponding terminal. ",
    "3-2": "9876543212",
    "4-0": "order_id",
    "4-1": "It represents the ID created by you to identify the order for which the refund is initiated.",
    "4-2": "sampleorder0413",
    "5-0": "bank_reference",
    "5-1": "It represents the bank reference number for the transaction.",
    "5-2": "234928698581",
    "6-0": "refund_currency",
    "6-1": "It represents the currency of the refund amount.",
    "6-2": "INR",
    "7-0": "refund_amount",
    "7-1": "It represents the refunded amount.",
    "7-2": "2",
    "8-0": "refund_type",
    "8-1": "It represents the refund type. The value will always be PAYMENT_AUTO_REFUND.",
    "8-2": "PAYMENT_AUTO_REFUND",
    "9-0": "refund_arn",
    "9-1": "It represents the bank reference number for the refund.",
    "9-2": "205907014017",
    "10-0": "refund_status",
    "10-1": "It represents the status of the refund (either SUCCESS or INITIATED)",
    "10-2": "SUCCESS",
    "11-0": "status_description",
    "11-1": "It represents the description of the refund status  \n(Two possible values:  \n Auto-Refund initiated successfully or  \nAuto-Refund processed successfully).",
    "11-2": "Auto-Refund initiated successfully",
    "12-0": "created_at",
    "12-1": "It represents the time of auto-refund creation.",
    "12-2": "2022-02-28T12:54:25+05:30",
    "13-0": "processed_at",
    "13-1": "It represents when the auto-refund was processed successfully.",
    "13-2": "2022-02-28T13:04:27+05:30",
    "14-0": "refund_reason",
    "14-1": "It represents the reason of initiation of Auto-refund  \n(Possible values:  \nCredit was received for an incomplete payment.  \nRefunded to customer for Dispute.  \nPayment made directly to your VPA without order creation.  \nMultiple payments were performed against same order.  \nPayment details (amount, bank, etc.) do not match with created order or the payment was made after TTL.)",
    "14-2": "Multiple payments were performed against same order",
    "15-0": "refund_charge",
    "15-1": "It represents the charges for processing refund in INR.",
    "15-2": "0",
    "16-0": "refund_splits",
    "16-1": "It represents the refund split details.",
    "16-2": "\\[]",
    "17-0": "metadata",
    "17-1": "It represents the additional metadata.",
    "17-2": "null",
    "18-0": "event_time",
    "18-1": "It represents when the refund webhook was initiated.",
    "18-2": "2022-02-28T13:04:28+05:30",
    "19-0": "type",
    "19-1": "It represents the webhook type. The value will always be AUTO_REFUND_STATUS_WEBHOOK.",
    "19-2": "AUTO_REFUND_STATUS_WEBHOOK"
  },
  "cols": 3,
  "rows": 20,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


***

# Terminal Status Update Webhook Version: (2022-09-01)

The new terminal status update webhook notifies you about the terminal status update, and gives you comprehensive information about terminal updates.

<pre><code>{
"data":{
"added_on":string"2024-03-07 15:11:02"
"cf_terminal_id":int1234
"last_updated_on":string"2024-04-26 12:16:08"
"terminal_id":int1233
"terminal_name":string"ABC"
"terminal_phone":string"9696969696"
"terminal_status":string"PROVISIONALLY_ACTIVE"
"terminal_type":string"STOREFRONT"
"review_remarks":string"approved"
}
"event_time":string"2024-04-26T12:16:08+05:30"
"type":string"TERMINAL_STATUS_UPDATE"
}</code></pre>

# Dispute Webhooks Version: (2022-09-01)

Dispute webhooks can be configured to receive automated notifications when disputes are created, updated and closed.

The webhook notification will be sent on all the URLs added and enabled under the dispute webhook. Merchants can add new URLs and enable or disable existing URLs for refund webhook at any point in time and it will be reflected instantaneously.

| Webhook         | Description                                                                                                                                                                                                                                             |
| :-------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| DISPUTE_CREATED | Dispute_created webhook will be triggered when a new dispute is created.                                                                                                                                                                                |
| DISPUTE_UPDATED | Dispute_updated webhook will be triggered when a dispute is updated, for example when a comment is added by the Cashfree team, when the dispute moves into further stages like Pre-arbitration, Arbitration, or when the status of the dispute changes. |
| DISPUTE_CLOSED  | This webhook will be triggered when a dispute is closed.                                                                                                                                                                                                |

### Dispute Created

**Sample Payload**

<pre><code>{
    "data": {
        "dispute": {
            "dispute_id": "433475258",
            "dispute_type": "DISPUTE",
            "reason_code": "1402",
            "reason_description": "Duplicate Processing",
            "dispute_amount": 3,
            "created_at": "2023-06-15T21:49:48+05:30",
            "updated_at": "2023-06-15T21:49:48+05:30",
            "respond_by": "2023-06-18T23:59:59+05:30",
            "dispute_status": "DISPUTE_CREATED",
            "cf_dispute_remarks": "Dispute is created, please take action",
            "dispute_action_on": "MERCHANT"
        },
        "order_details": {
            "order_id": "order_1944392DR1kMTFYdIf8bI2awAcC3i9FTa",
            "order_amount": 3,
            "order_currency": "INR",
            "cf_payment_id": 885473311,
            "payment_amount": 3,
            "payment_currency": "INR"
        },
        "customer_details": {
            "customer_name": "Dileep Kumar s",
            "customer_phone": "8000000000",
            "customer_email": "dileep@gmail.com"
        },
        "terminal_details": {
            "cf_terminal_id": 989876,
            "terminal_phone": "9876543212"
        }
    },
    "event_time": "2023-06-15T21: 50: 04+05: 30",
    "type": "DISPUTE_CREATED"
}
</code></pre>

***

### Dispute Updated

**Sample Payload**

<pre><code>{
    "data": {
        "dispute": {
            "dispute_id": "433475257",
            "dispute_type": "PRE_ARBITRATION",
            "reason_code": "13.1",
            "reason_description": "Merchandise / Services Not Received",
            "dispute_amount": 40000,
            "created_at": "2023-06-15T21:16:03+05:30",
            "updated_at": "2023-06-15T21:19:15+05:30",
            "respond_by": "2023-06-19T23:59:59+05:30",
            "dispute_status": "PRE_ARBITRATION_CREATED",
            "cf_dispute_remarks": "Pre Arbitration request has been raised for this case.\\nTarget Date :: 2023-06-18T00:00 -> 2023-06-19T23:59:59.",
            "dispute_update": "TYPE_UPDATE",
            "dispute_action_on": "MERCHANT"
        },
        "order_details": {
            "order_id": "order_1944392D4jHtCeVPPdTXkaUwg5cfnujQe",
            "order_amount": 40000,
            "order_currency": "INR",
            "cf_payment_id": 885457437,
            "payment_amount": 40000,
            "payment_currency": "INR"
        },
        "customer_details": {
            "customer_name": "Dileep Kumar s",
            "customer_phone": "8000000000",
            "customer_email": "dileep@gmail.com"
        },
        "terminal_details": {
            "cf_terminal_id": 989876,
            "terminal_phone": "9876543212"
        }
    },
    "event_time": "2023-06-15T21:20:24+05:30",
    "type": "DISPUTE_UPDATED"
}
</code></pre>

***

### Dispute Closed

**Sample Payload**

<pre><code>{
    "data": {
        "dispute": {
            "dispute_id": "433475257",
            "dispute_type": "CHARGEBACK",
            "reason_code": "4855",
            "reason_description": "Goods or Services Not Provided",
            "dispute_amount": 4500,
            "created_at": "2023-06-15T21:16:03+05:30",
            "updated_at": "2023-06-15T21:16:51+05:30",
            "respond_by": "2023-06-18T00:00:00+05:30",
            "resolved_at": "2023-06-15T21:16:51.682836678+05:30",
            "dispute_status": "CHARGEBACK_MERCHANT_WON",
            "cf_dispute_remarks": "Chargeback won by merchant"
        },
        "order_details": {
            "order_id": "order_1944392D4jHtCeVPPdTXkaUwg5cfnujQe",
            "order_amount": 4500,
            "order_currency": "INR",
            "cf_payment_id": 885457437,
            "payment_amount": 4500,
            "payment_currency": "INR"
        },
        "customer_details": {
            "customer_name": "Dileep Kumar s",
            "customer_phone": "8000000000",
            "customer_email": "dileep@gmail.com"
        },
        "terminal_details": {
            "cf_terminal_id": 989876,
            "terminal_phone": "9876543212"
        }
    },
    "event_time": "2023-06-15T21:17:14+05:30",
    "type": "DISPUTE_CLOSED"
}
</code></pre>

### Payload Field Description

[block:parameters]
{
  "data": {
    "h-0": "Field",
    "h-1": "Description",
    "h-2": "Example",
    "h-3": "Type",
    "0-0": "dispute_id",
    "0-1": "Cashfree’s unique ID to identify a dispute.",
    "0-2": "433475257",
    "0-3": "Long",
    "1-0": "dispute_type",
    "1-1": "Type of dispute created. Possible values:  \n- DISPUTE  \n-  RETRIEVAL  \n- CHARGEBACK  \n- PRE_ARBITRATION  \n- ARBITRATION",
    "1-2": "Chargeback",
    "1-3": "String",
    "2-0": "cf_terminal_id",
    "2-1": "Cashfree Payments Terminal ID of the payment for which refund is initiated.",
    "2-2": "989876",
    "2-3": "Long",
    "3-0": "terminal_phone",
    "3-1": "The phone number of the corresponding terminal. ",
    "3-2": "9876543212",
    "3-3": "String",
    "4-0": "reason_code",
    "4-1": "Condition for which the customer is filing the case. Click [here](doc:dispute-reason-codes) to know more about dispute reason codes.",
    "4-2": "13.6",
    "4-3": "String",
    "5-0": "reason_description",
    "5-1": "Description of the reason code. Codes for Chargeback cases are specified by Card networks/NPCI.",
    "5-2": "Credit not processed",
    "5-3": "String",
    "6-0": "dispute_amount",
    "6-1": "The amount for which the dispute has been created.",
    "6-2": "4500",
    "6-3": "BigDecimal",
    "7-0": "created_at",
    "7-1": "Time on which the dispute was registered on Cashfree’s system.",
    "7-2": "2023-06-15T21:16:03+05:30",
    "7-3": "LocalDateTime",
    "8-0": "updated_at",
    "8-1": "Time on which the dispute was updated.",
    "8-2": "2023-06-15T21:16:51+05:30",
    "8-3": "LocalDateTime",
    "9-0": "respond_by",
    "9-1": "Time by which the merchant is expected to respond to the dispute.",
    "9-2": "2023-06-18T00:00:00+05:30",
    "9-3": "LocalDateTime",
    "10-0": "dispute_status",
    "10-1": "Status of Dispute. All possible values are listed in the table below.",
    "10-2": "CHARGEBACK_CREATED",
    "10-3": "String",
    "11-0": "cf_dispute_remarks",
    "11-1": "Any remarks specified by Cashfree on the dispute.",
    "11-2": "Please submit documents.",
    "11-3": "String",
    "12-0": "dispute_update",
    "12-1": "Specifies what has been updated on the dispute. Possible Values:  \n- STATUS_UPDATE  \n- TYPE_UPDATE  \n- COMMENT_UPDATE",
    "12-2": "TYPE_UPDATE",
    "12-3": "String",
    "13-0": "dispute_action_on",
    "13-1": "Specifies whether the action is on Cashfree or Merchant at a time.  \nPossible Values:  \n- MERCHANT  \n- CASHFREE",
    "13-2": "MERCHANT",
    "13-3": "String",
    "14-0": "resolved_at",
    "14-1": "Time on which the dispute was resolved/closed.",
    "14-2": "2023-06-15T21:16:51.682836678+05:30",
    "14-3": "LocalDateTime",
    "15-0": "event_time",
    "15-1": "Time at which dispute webhook was initiated.",
    "15-2": "2023-06-15T21:16:51+05:30",
    "15-3": "LocalDateTime",
    "16-0": "type",
    "16-1": "Type of webhook. Possible Values:  \n- DISPUTE_CREATED  \n- DISPUTE_UPDATED  \n- DISPUTE_CLOSED",
    "16-2": "DISPUTE_CREATED",
    "16-3": "String"
  },
  "cols": 4,
  "rows": 17,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]
