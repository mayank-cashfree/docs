---
title: "BaaS Virtual Account"
slug: "baas-virtual-account"
excerpt: ""
hidden: true
createdAt: "Wed May 11 2022 06:33:20 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Dec 05 2023 13:45:30 GMT+0000 (Coordinated Universal Time)"
---
Cashfree Payments new product **Accounts** enables you to quickly integrate banking services from leading banks into your product via APIs. Enable your users to open accounts, link accounts, accept deposits, make payouts, check balances, earn interest, and more.

***

**Why Cashfree Payments Accounts?**

Cashfree Payments BaaS platform **Accounts** allows you to create payment instruments for your customers and facilitate different financial and non-financial operations like fund transfer, fetch balance, and others.

We have done complex integrations with leading banks so that you don't have to invest in bank integration, compliances and other operational processes.

Get notified in real-time on all the activities related to accounts creation, money transfer and other day-to-day operations.

Contact [care@cashfree.com](mailto:care@cashfree.com) to get this product activated for your account.

Example: 

- Let us say that you own an HRMS platform, and you want to increase engagement by providing more tailored banking services. You decide to allow corporates to open bank accounts for their employees with almost no paperwork. You can achieve this using our APIs or by using our intuitive and powerful product dashboard.

- For an e-commerce platform, you can reward your customers with loyalty points. To do this, you decide to issue a prepaid card with your brand name on it, and as soon as customers spend using the card, you will post the cash-back on the card. This will allow you to analyse their spending behaviours and offer more tailored products, strengthening retention and engagement.

For either of the use cases, if you decide to do it yourself, it could take you a lot more effort and time to manage multiple banking integrations or flows. Our BaaS solution Accounts makes it easy and simple to manage multiple payment instrument related activities seamlessly.

***

# API Host

Cashfree Payments platform provides a sandbox environment where you can explore the capabilities of our API Banking suite. We recommend you do all developmental activities and testing in the sandbox environment. All activity in the Production environment will be billed. Once you have tested in the sandbox and are ready to deploy, we will complete your KYC process and enable the production environment for you to go live.

Refer to the below links for help with API Keys authentication and handling error responses.

**[Common API Authentication](ref:api-authentication)**  
**[Common Error Handling](ref:error-handling)**

***

# BaaS Virtual Account

BaaS Virtual account is a digital/online account which is built on the current/nodal/escrow account, each virtual account acts as a sub-account of the particular account that it is linked to. 

BaaS Virtual account is a digital account which allows your customers to perform all operations that a current account can. Your customer can add funds to their BaaS virtual account and can transfer them to their respective beneficiaries. They can fetch balances, and transfer funds without the hassle of multiple levels of documentation. BaaS Virtual Accounts are created on top of our escrow account and enable seamless payments, support statements, balance check features, and more.

Cashfree Payments provides an admin dashboard where you can explore features of our banking as a service suite, aggregate customer and instrument details and also make informed decisions based on our reports. The dashboard can also be used to initiate account opening requests. All the features on the dashboard are also offered through our APIs. We recommend using our APIs for faster creation and enablement of BaaS virtual accounts for multiple customers at one go.

Every customer is given an account number and an IFSC for their BaaS virtual account. We create a BaaS Virtual Account when your customer completes the API based KYC and gives their consent.  
To use the BaaS Virtual Account for collections and disbursals, your customers need to first add funds to their BaaS virtual account. The fund can be added directly from your customer’s registered bank account, or through the collection flow (PG, QR code-based) that you can enable through your platform. To know more about how to enable collections for your customers and provide the right solution that works for your business, you can reach out to our team. 

BaaS Virtual Account supports a wide range of payment methods such as IMPS, NEFT and UPI. This gives your customer the flexibility to make payments to their parties using any of these methods that they are comfortable with.

***

# Customer Details

You can add customer details using: 

- [Accounts APIs](doc:virtual-account#add-customer-details-using-api)
- [Accounts Dashboard](doc:virtual-account#add-customer-details-using-dashboard)

### Add Customer Details Using API

The following APIs will help you to create, edit, and delete customer details.

**[Create Customer](ref:customers)**- Allows you to create a customer.  
**[Get customer details](ref:get-customer)**- Allows you to fetch and view customer details of a specific customer.  
**[Get multiple customer details](ref:get-customers)**- Allows you to fetch and view customer details of multiple customers at the same time.  
**[Edit Customer Details](ref:edit-customer)**- Allows you to edit existing customer details like customer type, full name, email address and phone number.  
**[Delete Customer](ref:delete-customer-instrument)**- Allows you to delete a customer.

If you face any errors while adding your customer details, check [Customer Error Codes](ref:customers-errors) for details.

***

### Add Customer Details Using Dashboard

To add customer details, 

1. Go to Account Dashboard > click **Add Customer**.
2. Enter **Customer ID**. It must a unique ID for each customer, and it must include special characters (\_,\*,).
3. Enter the customer's **Full Name**.
4. Select the **Type** of business for the customer, if they are individual or business.
5. Enter the customer **Phone Number**.
6. Enter the customer **Email ID** and click **Add Customer**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b3b1811-Screenshot_2022-05-23_at_8.06.06_AM.png",
        "Screenshot 2022-05-23 at 8.06.06 AM.png",
        368
      ],
      "border": true,
      "caption": "Add Customer"
    }
  ]
}
[/block]


You can view the customer details you have added in the Customers screen as shown below:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/48e9160-Screenshot_2022-05-23_at_8.25.33_AM.png",
        "Screenshot 2022-05-23 at 8.25.33 AM.png",
        1432
      ],
      "border": true,
      "caption": "Customers"
    }
  ]
}
[/block]


***

# Customer KYC

To create a virtual account for your customer, the KYC procedure must be complete. To help you with the KYC verification, we support [Add Customer KYC](ref:add-customer-kyc) API and [Get Customer KYC](ref:get-customer-kyc) API. Every customer is given an account number and an IFSC for their BaaS virtual account.

### Impact of KYC workflow in virtual account creation:

- KYC can be used to verify customer details during onboarding to establish legitimacy.
- KYC helps prevent money laundering activities and manage risk better.

### Steps to Integrate

- KYC checks will be enabled by the Cashfree Payments team.
- Merchant is required to integrate the KYC suite offered as part of the BaaS Accounts product. The links for the APIs are below:  
          _   [Add Customer KYC](ref:add-customer-kyc)  
          _   [Get Customer KYC](ref:get-customer-kyc)
- After a customer is created using [Create Customer](ref:customers) API, the customer needs to complete KYC for all the required documents.
- For each customer, merchants are required to call the respective KYC API based on the customer type (defined below in the table) and ensure the KYC is completed successfully.
- When a user creates a virtual account - we fetch KYC status with customer_id.
- If the required KYC is completed, then we let the user create a virtual account. Otherwise, we do not allow the customer to create a virtual account.

The documents required for various customer types are shown below:

[block:parameters]
{
  "data": {
    "h-0": "Document",
    "h-1": "Individual",
    "h-2": "Proprietorship",
    "h-3": "HUF",
    "h-4": "Partnership",
    "h-5": "LLP",
    "h-6": "Private Limited/Public)ltd/ OPC",
    "h-7": "NGO/Trust/Society",
    "0-0": "PAN CARD",
    "0-1": "Yes\\*  \n(Personal PAN)",
    "0-2": "Yes\\*  \n(Personal PAN)",
    "0-3": "Yes  \n(Authorised Signatory)",
    "0-4": "Yes  \n(Authorised Signatory)",
    "0-5": "Yes  \n(Authorised Signatory)",
    "0-6": "Yes  \n(Authorised Signatory)",
    "0-7": "Yes  \n(Authorised Signatory)",
    "1-0": "AADHAAR  \nPersonal/Authorised Signatory",
    "1-1": "Yes  \n(Personal Aadhaar)",
    "1-2": "Yes  \n(Personal Aadhaar)",
    "1-3": "Yes  \n(Authorised Signatory)",
    "1-4": "Yes  \n(Authorised Signatory)",
    "1-5": "Yes  \n(Authorised Signatory)",
    "1-6": "Yes  \n(Authorised Signatory)",
    "1-7": "Yes  \n(Authorised Signatory)",
    "2-0": "Bank Account Verification",
    "2-1": "Yes\\*",
    "2-2": "Yes\\*",
    "2-3": "Yes\\*",
    "2-4": "Yes\\*",
    "2-5": "Yes\\*",
    "2-6": "Yes\\*",
    "2-7": "Yes\\*",
    "3-0": "Business/Company PAN Card",
    "3-1": "-",
    "3-2": "-",
    "3-3": "Yes\\*",
    "3-4": "Yes\\*",
    "3-5": "Yes\\*",
    "3-6": "Yes\\*",
    "3-7": "Yes\\*",
    "4-0": "GST Certificate",
    "4-1": "-",
    "4-2": "Yes\\*",
    "4-3": "Yes\\*",
    "4-4": "Yes\\*",
    "4-5": "Yes\\*",
    "4-6": "Yes\\*",
    "4-7": "Yes\\*"
  },
  "cols": 8,
  "rows": 5,
  "align": [
    "left",
    "left",
    "left",
    "left",
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


[ * We verify the name in the document against the customer's name. The **Name Matching** feature will be available soon. Currently, it is available only for Bank Account Verification.]

***

# Payment Instruments

After adding customer details, you can create payment instruments for customers. Cashfree Payments supports the following payment instruments:

- Current Accounts 
- Savings Accounts
- Virtual Accounts 
- Cards - Prepaid Cards

# Create and Manage BaaS Virtual Account

The following APIs will help you to create and manage BaaS virtual accounts for your customers. After you create BaaS virtual accounts for your customers, they can recharge them via their bank by adding the virtual account details as beneficiaries on their net banking portal or they can also recharge this virtual account via UPI where all they have to do is log into their UPI account and add the BaaS virtual account details there (A/c number, IFSC and Name).

- [Create BaaS Virtual Account](ref:create-virtual-account) - Allows you to create a virtual bank account for your customer.
- [Get BaaS Virtual Account](ref:get-virtual-account) - Allows you to get the details of a customer's virtual account.
- [Get BaaS Virtual Account Balance](ref:get-virtual-account-balance) - Allows you to get the balance of a customer's virtual account.

If you face any errors while creating a BaaS virtual account for your customers, check [Payment Instruments Error Codes](ref:payment-instruments-errors) for details.

## View BaaS Virtual Account Balance and Statements

You can enable your customers to view their BaaS virtual account balance and statement data using the following APIs:

### View Balance

You can enable your customer to view their BaaS virtual account balance along with the timestamp of when the balance was last updated on using our [Get BaaS Virtual Account Balance](ref:get-virtual-account-balance) API.

### View Statement

Your customers can also get details about their BaaS virtual account statement. Use our [Get BaaS Virtual Account Statement](ref:get-virtual-account-statement) API to get the statement details.

# Create and Manage Beneficiaries

To initiate transfers, your customers must first add the beneficiary details. They must first add the name, email ID, phone number, and bank details of the beneficiary account to whom they want to make the transfer. Bank or UPI details are required to initiate transfers to beneficiary. There is no limit to the number of beneficiaries that you can add.

The beneficiary ID must be unique for each beneficiary. This is required to initiate transfers.  
You can enable your customer to create, view, delete beneficiaries using the APIs mentioned below:

- [Create Beneficiary](ref:api-create-beneficiary)
- [Get Beneficiary Details](ref:get-beneficiary)
- [Get multiple Beneficiaries’ Details](ref:get-beneficiaries)
- [Delete Beneficiary](ref:delete-beneficiary)

If you face any errors while creating or managing beneficiaries, check [Beneficiary Error Codes](ref:beneficiary-error-codes) for details.

***

# Make Transfer

You can enable your customer to make transfers from their BaaS virtual account to a beneficiary account. Customers can transfer after adding funds to their BaaS virtual account. They need to have a sufficient balance in the account to make a payout. We support Bank and UPI transfer methods. Transfers once confirmed, cannot be reversed.

You can also initiate direct transfers to beneficiary account without creating a beneficiary account for a customer at Cashfree Payments using the [Request Direct Transfer](ref:request-direct-transfer) API.

- [Request Transfer](ref:request-transfer) - This API allows you to initiate an amount transfer request to a customer’s instrument at Cashfree Payments. This is an async transfer request.
- [Request Direct Transfer](ref:request-direct-transfer) - This API allows you to initiate an amount transfer request directly to the beneficiary account without creating a beneficiary for a customer at Cashfree Payments. This is an async transfer request.
- [Get Transfer](ref:get-transfer) - Use this API to get the details of a specific transfer by providing the transfer_id.
- [Get Multiple Transfers](ref:get-transfers) - Use this API to get details of multiple transfers of a customer.
- [Internal Transfer](ref:baas-internal-transfer) - Use this API to transfer an amount from a BaaS virtual account to a customer’s virtual account. This is a synchronous transfer request.

If you face any errors during transfers, check [Transfer Error Codes](ref:transfer-error-codes) for details.

## Self Withdrawal

To withdraw funds from BaaS virtual account, your customers must add their own bank account details as beneficiaries and make the transfer.

## BaaS Merchant Wallet and Internal Transfer

A BaaS Virtual Account can be created specifically for the merchant. To do this, first an internal customer must be created. To do this, please write to [care@cashfree.com](mailto:care@cashfree.com) or reach out to your account manager.

Transfers can be made from the BaaS Merchant Virtual Account to BaaS Customer Virtual Account using the BaaS [Internal Transfer](ref:baas-internal-transfer) API. The required Customer Virtual Account details can be passed in the API request body along with the Instrument ID of the BaaS Merchant Virtual Account. The transfer will then be initiated from the BaaS Merchant VA to the BaaS Customer VA. 

## Lifecycle

When your customer transfers money from their BaaS virtual account there are various states that the transaction goes through before reaching the beneficiary account. The various states help you understand the status of the transaction.

Cashfree Payments supports an asynchronous lifecycle for virtual account transactions.  
In an asynchronous lifecycle, users do not have to wait to see the final state, you get a response that your request has been received. The final status will be sent with the help of webhooks.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dc9bf76-payouts-lifecycle-2.png",
        "payouts-lifecycle-2.png",
        653
      ],
      "border": true,
      "caption": "Payouts Asynchronous Lifecycle"
    }
  ]
}
[/block]


### Received

When the transfer request has been received, the payout is in the Received state. It then processes the request further if the details provided are accurate.  
It can transition into the Rejected state if the details provided are incorrect. The user has to reinitiate the payout.

### Rejected

When the payout request has incorrect beneficiary account details, the payout is in the Rejected state. Rejected is a final state and does not allow transitioning to any other state.

You can view the transfer status in the Payout Dashboard or use the API [Get Transfer Status](ref:get-transfer-status) or webhooks to know the status.

### Pending

When the transfer status is yet to be confirmed, the payout is in the Pending state. At this point, the partner bank could be processing the payout and no further action is required from your end.

The Pending state can transition into:

- Success state, if the payout is successful.
- Failed state, if the payout fails.

### Failed

When the payout request fails, the payout is in the Failed state. Failed is a final state and does not allow transitioning to any other state. You can reinitiate the transfers which have failed. 

For failed transfers, if any amount is debited, it will be reversed to you by the remitter bank within 24 hours.

A payout can indicate a Failed state due to various reasons, such as:

- The beneficiary account details are wrong and not validated. To avoid this, you can validate the beneficiary account details using the [Bank Account Verification](doc:verify-bank-account-details) feature.
- There is no sufficient balance in your Payouts recharge account. To avoid this, you can specify the balance in the [Low Balance Alert](doc:manage-funds#set-low-balance-alert) section, if the balance goes below the amount specified, Cashfree will send you a notification.
- Remitter or beneficiary bank servers are down.

### Success

When the remitter's bank has completed the transfer, the payout is in the Success state.

The Success state can transition into the Reversed state if the transfer is reversed by the beneficiary bank.

### Reversed

A payout can be in the Reversed state due to various reasons, such as:

- Incorrect account details
- Reversal by the clearinghouse
- Reversal by the beneficiary bank

Reversed is a final state and does not allow transitioning to any other state.

***

# VPA for Collections with BaaS VAs

We offer unique upi vpa against each BaaS virtual account creation. This will help in enabling collections via UPI QR or UPI mode into the BaaS VA of the customer.With this Cashfree will also enable transaction wise settlement into the customer ledger.

Fintechs/Neobanks can now enable collections for BaaS accounts in a compliant manner. These vpas are created on Cashfree PA escrow which is a compliant escrow account to facilitate collections.

### How will this work?

- This feature needs to be enabled once from the Cashfree side
- In the virtual account creation api, Cashfree will respond with the vpa associated with it. you can refer the documentation for this api [Create Virtual Account](ref:create-virtual-account) 
- Merchants can educate their customers to use scan QR mode to enable collections on their BaaS  
   account.
- Given this workflow is built on top of different (PA escrow), the funds movement is something  
   you need to understand here as we are enabling Transaction Wise Settlement into the Customer BaaS VA.
- Movement of actual funds from PA Escrow to BaaS Escrow (Internal Master BaaS VA of Merchant) will happen in every hour interval during banking hours. To facilitate real time settlements, merchants will be required to maintain balance in the Master Internal BaaS VA to cover for the lack of funds due to delayed arriving of funds from PA Escrow.
- Although, if the funds are available in Master Internal BaaS VA of the merchant, the transactions will get reflected/settled real time in the corresponding Customer BaaS VA. [Cashfree will perform this operation of credit in Customer’s BaaS VA whenever transaction notification is received by Cashfree on the issued vpa]
- If the required funds are not available in Master BaaS VA, these real time credits will fail and will get credited as and when funds are made available in that master VA account [Merchant can park some funds there to facilitate real time settlement]

# Webhooks

Webhooks are server callbacks to your server from Cashfree. Webhooks are event-based and are sent when specific events related to the transaction or instrument happen. Webhooks help you receive automatic updates and are significant for completing the integration with Cashfree.

Cashfree Payments sends the following webhooks:

1. [Instrument](https://docs.cashfree.com/reference/instrument-webhooks)
2. [Transfer](https://docs.cashfree.com/reference/transfer-webhooks) 

To configure webhooks,

1. Go to the Merchant dashboard > **Accounts Dashboard** > **Developers** > click **Webhook** in the **API Banking** section.
2. In the **Developers - Banking** screen, click **Add Webhooks**.
3. Choose the **Webhook Type** and then **Webhook Sub Type** based on your requirement.
4. Enter the URL where you want to receive the updates about the BaaS events. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8975040-Screenshot_2022-05-05_at_6.55.29_PM.png",
        "Screenshot 2022-05-05 at 6.55.29 PM.png",
        2859
      ],
      "caption": "Add Webhook"
    }
  ]
}
[/block]


5. Click **Test & Add Webhook**.

```json Sample Payload
{
  "data": {
    "transfer": {
      "customer_id": "cust_123",
      "transfer_id": "transfer_123",
      "instrument_id": "inst_123",
      "bank_reference_number": "1639124531203578"
    }
  },
  "type": "TRANSFER_SUCCESS",
  "version": 1,
  "event_time": "2022-02-06T05:33:55Z"
}
```

### Signature Verification

Cashfree Payments sends a signature and timestamp alongside every webhook in headers named: **X-Cashfree-Signature **and **X-Cashfree-Timestamp**. Verifying this signature (passed along with the POST parameters ) is mandatory before processing any response. It helps authenticate that the webhook is from Cashfree BaaS Product and verify if the request has not been tampered with.

**Following are the steps to verify Cashfree BaaS events signature:**

To verify the signature at your end, you will need your oldest Cashfree ACTIVE BaaS Account secret key.

```text Signature Verification
timestamp := 1617695238078; 
signedPayload := $timestamp.$payload;
expectedSignature := Base64Encode(HMACSHA256($signedPayload, $merchantSecretKey));
```

### Webhook Retries

Cashfree webhooks service does its best to deliver events to your webhook endpoint. It is best practice for your application to respond to the callback. Our webhook service may send many payloads to a single endpoint in quick succession. You will need to build an application and configure your server to receive the response we send when events get triggered during the process.

Your server should return a 200 HTTP status code to acknowledge that you received the webhook without any issues. Any other information you return in the request headers or request body gets ignored. Any response code outside the 200 range, including 3xx codes, indicates that you did not receive the webhook.

When Cashfree Payments does not get the acknowledgment due to any reason, we retry to establish the communication at regular intervals. If we do not receive a response after a few attempts, we gradually decrease the rate of retries. Based on this count, the service is disabled if it fails more than five times.

If you do not receive notifications from Cashfree Payments as expected, contact our support team at [care@cashfree.com](mailto:care@cashfree.com).

***

# References

## Bank Transfers

Bank transfers via Cashfree Payments supports both the IMPS and NEFT payouts. By default, IMPS is the configured mode for payouts, since deposits made using IMPS are instantly credited to the beneficiary account.

Below is the comparison between IMPS and NEFT. You can select the required payment method as per your need.

| IMPS                                                                                       | NEFT                                                                                                                   |
| :----------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------- |
| IMPS is an instant transfer the amount is credited to the beneficiary account immediately. | NEFT ideally takes up to 2 hours to reflect in the beneficiary account.                                                |
| IMPS is available at all times.                                                            | NEFT is available between 1 AM and 6:45 PM on all NEFT working days (Monday to Saturday, except 2nd and 4th Saturday). |
| IMPS has a limit of Rs. 2 lakhs per payout.                                                | NEFT is the default payout method for any amount higher than Rs. 2 lakhs.                                              |

You need the beneficiary ID, name, email, phone, bank account number, and IFSC to add a beneficiary for bank payouts. If the bank account details or IFSC is incorrect, the transfer fails.

## UPI Transfers

UPI payouts can be made at all times including weekends and holidays. With instant payouts, you can immediately send funds to all valid UPI VPAs.

> 📘 The transaction limit per UPI payouts is Rs. 1 lakh. Although the transaction limit is Rs. 1 Lakh, the upper limit might vary from bank to bank. This limit ranges from Rs. 10,000 to Rs. 1 lakh.
> 
> You need to provide a valid UPI VPA for the payouts to go through. No other beneficiary details are required. If the provided VPA is incorrect, then the payout fails on initiation.

You need the beneficiary ID, name, email, phone, and VPA to add a beneficiary for UPI payouts. If the VPA is incorrect, the transfer fails.

***

# Frequently Asked Questions

Click [here](doc:baas-faq) to see some of the frequently asked questions and solutions for the same.
