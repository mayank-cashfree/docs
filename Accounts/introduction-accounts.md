---
title: "Introduction -  BaaS WIP"
slug: "introduction-accounts"
excerpt: ""
hidden: true
createdAt: "Tue Sep 13 2022 09:45:51 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Dec 05 2023 13:45:31 GMT+0000 (Coordinated Universal Time)"
---
# Banking as a Service

Banking as a Service (BaaS) refers to utilising the APIs to allow third parties to provide services that were traditionally provided by the banks which are directly accessible to  customers via these BaaS merchants and built on top of bank provided regulated infrastructure. 

Cashfree Payments new product Accounts enables you to quickly integrate banking services from leading banks into your product via APIs. Enable your users to open accounts, link accounts, accept deposits, make payouts, check balance, earn interest, and more. 

***

# Why Cashfree Payments BaaS?

Cashfree Payments BaaS platform **Accounts** allows you to create payment instruments for your customers and facilitate different financial and non-financial operations like fund transfer, fetch balance, and others.

We have done complex integrations with leading banks so that you don't have to invest in bank integration, compliances and other operational processes. When you use the Accounts API, Cashfree interacts with our partner banks servers and create a new account within minutes.With our easily integrable and highly efficient APIs, You can overcome the problems with tedious integrations, Limited TPS, difficult reconciliation and single A/c dependancy.

Get notified in real-time on all the activities related to accounts creation, money transfer and other day-to-day operations.

Contact [care@cashfree.com](mailto:care@cashfree.com) to get this product activated for your account.

Example: 

### Neo Banks:

A neo-bank focussed API stack that enables seamless collections & disbursals, card issuance & credit line - all in one place

### NBFCs and Lending Platforms:

Smart Accounts on top of NBFC Escrow and Current Accounts to enable Credit Line with custom disbursal & repayment flows

### Payroll Platforms

Complete API stack for payroll disbursal - use our smart accounts APIs to enable bulk disbursals from your platform; issue payroll cards for gig workers

### SaaS Invoicing and ERP Platforms:

Embed payments for Account Payable & Receivables for your customers on your dashboard 

For either of the use cases, if you decide to do it yourself, it could take you a lot more effort and time to manage multiple banking integrations or flows. Cashfree's Accounts makes it easy and simple to manage multiple payment instrument-related activities seamlessly.

# Customer Entity

Cashfree Payments BaaS platform **Accounts** allows you to create payment instruments for your customers and facilitate different financial and non-financial operations like fund transfer, fetch balance, and others. Customers here are referred to as your business customers.

Cashfree currently supports two type of customer namely - 

- Individual
- Proprietorship
- Partnership
- Private Limited.
- Public Limited
- LLP
- HUF
- OPC  
  You are required to categorise your business customers accordingly. This is required for regulatory requirements and applicability of subsequent functions like issuance of specific payment instrument is governed by the type of the customer.

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

## Payment Instruments

Cashfree Payments brings to you a curated banking experience that enables you to create payment instruments for your customers and perform subsequent financial and non-financial operations on these instruments. 

Payment instruments are different modes through which a user can either disburse or collect payments. Either banks or non-banking financial entities issue payment instruments.

Currently, we support the following payment instruments:

# Accounts 

## BaaS Current Account:

Cashfree Payments enables you to seamlessly open current accounts for your customers and once the account is created and linked to our BaaS solution Accounts, our APIs will help your customers to make payments, check their balances and fetch their bank statements on your platform.

To know more about BaaS Current Accounts - [BaaS Current Account](doc:current-account) 

## BaaS Virtual Account:

BaaS Virtual account is a digital/online account which is built on the current/nodal/escrow account, each virtual account acts as a sub-account of the particular account that it is linked to. 

To know more about BaaS Current Accounts - [BaaS Virtual Account](doc:baas-virtual-account) 

- Cards - Prepaid Cards  
  ---- add desc---

***

## Accounts Workflow

1. Integrate Cashfree Payments Accounts into your product using our APIs.
2. Cashfree partner banks will be displayed on your app.
3. Your users can select the preferred bank, enter name and upload identification documents.
4. Cashfree authenticates KYC details at the backend by calling banks API.  
   _- On-site verification is mandatory for current accounts_
5. On successful verification, an account is created for your user.

Your users can access their accounts through your product to accept deposits, make payouts, check balances, earn interest, and more.

## Create and Manage Customers

Cashfree APIs and an easy to use dashboard allow you as a merchant to cater to the banking needs of your customers by issuing them different payment instruments. Customers here are referred to as your business customers.

In this section, we will understand how to create, edit, view or delete customers on the Cashfree Payments platform. You can read more about creating and managing customers in the following link:  
[Create and Manage Customers](doc:api-banking-customers) 

## Manage Payment Instruments

Cashfree currently supports Bank Accounts as a payment instrument. Stay tuned to this page to know more about upcoming payment instruments.  
[Payment Instruments](doc:instruments) 

## Reports

Cashfree Payments Accounts dashboard allows you to generate intelligent reports to ease out your business reporting requirements. Generate a .xlsx report using the smart filters and multiple other features the way you want in minutes.

You can access all the previous generated reports as well by selecting the time range or using the filters. Navigate to the **Reports** section. You can read more on reports from the following link:  
[Reports](doc:accounts-reports)

## Payouts

This section has two views:

- Beneficiaries - View Details of beneficiaries added.
- Transfers - View Details of all Transfers.

You can read more on reports from the following link:  
[Payouts](doc:payouts-2)

## Collections

We offer unique upi vpa against each BaaS virtual account creation. This will help in enabling collections via UPI QR or UPI mode into the BaaS VA of the customer.With this Cashfree will also enable transaction wise settlement into the customer ledger. 

You can read more about this in [BaaS Virtual Account](doc:baas-virtual-account)
