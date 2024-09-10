---
title: "BaaS Current Account"
slug: "current-account"
excerpt: ""
hidden: true
createdAt: "Wed Apr 27 2022 07:19:17 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Dec 05 2023 13:45:30 GMT+0000 (Coordinated Universal Time)"
---
Cashfree Payments new product Accounts enables you to quickly integrate banking services from leading banks into your product via APIs. Enable your users to open accounts, link accounts, accept deposits, make payouts, check balance, earn interest, and more.

***

Why Cashfree Payments Accounts?

Cashfree Payments BaaS platform **Accounts** allows you to create payment instruments for your customers and facilitate different financial and non-financial operations like fund transfer, fetch balance, and others.

We have done complex integrations with leading banks so that you don't have to invest in bank integration, compliances and other operational processes. When you use the Accounts API, Cashfree interacts with our partner banks servers and create a new account within minutes.

Get notified in real-time on all the activities related to accounts creation, money transfer and other day-to-day operations.

Contact [care@cashfree.com](mailto:care@cashfree.com) to get this product activated for your account.

Example: 

- Let us say that you own an HRMS platform, and you want to increase engagement by providing more tailored banking services. You decide to allow corporates to open bank accounts for their employees with almost no paperwork. You can achieve this using our APIs or by using our intuitive and powerful product dashboard.

- For an e-commerce platform, you can reward your customers with loyalty points. To do this, you decide to issue a prepaid card with your brand name on it, and as soon as customers spend using the card, you will post the cash-back on the card. This will allow you to analyse their spending behaviours and offer more tailored products, strengthening retention and engagement.

For either of the use cases, if you decide to do it yourself, it could take you a lot more effort and time to manage multiple banking integrations or flows. Cashfree's Accounts makes it easy and simple to manage multiple payment instrument related activities seamlessly.

***

# Current Account

Cashfree Payments enables you to seamlessly open current accounts for your customers and once the account is created and linked to our BaaS solution Accounts, our APIs will help your customers to make payments, check their balances and fetch their bank statements on your platform.

Cashfree Payments provides an admin dashboard where you can explore features of our banking as a service suite, aggregate customer and instrument details and also make informed decisions based on our reports. The dashboard can also be used to initiate account opening requests. All the features on the dashboard are also offered through our APIs. We recommend using our APIs for a faster creation and enablement of current account for multiple customers at one go.

To open a current account with Cashfree Payments,

1. Add customer details. You can do this using the product dashboard or the API. You can also edit customer details when required.
2. Create a payment instrument for the customer. In this case, the payment instrument would be a current account for a customer.
3. Customers can open a new current account or add an existing current account with our partner banks. For new current account creation, you must complete an offline KYC procedure. For adding an existing current account with our partner bank no additional KYC process is required.
4. After the account is opened, you can activate connected banking to enable payouts, statement and balance checks and other features for the customer on your platform using our APIs.

***

# API Host

Cashfree Payments platform provides a sandbox environment where you can explore the capabilities of our API Banking suite. We recommend you do all developmental activities and testing in the sandbox environment. All activity in the Production environment will be billed. Once you have tested in the sandbox and are ready to deploy, we will complete your KYC process and enable the production environment for you to go live.

Refer to the below links for help with API Keys authentication and handling error responses.

**[Common API Authentication](ref:api-authentication)**  
**[Common Error Handling](ref:error-handling)**

***

# Customer Details

You can add customer details using: 

- [Accounts APIs](doc:add-customer-details-using-api)
- [Accounts Dashboard](doc:add-customer-details-using-product-dashboard)

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

# Payment Instruments

After adding customer details, you can create payment instruments for customers. Cashfree Payments supports the following payment instruments:

- Current Accounts 
- Savings Accounts
- Virtual Accounts 
- Cards - Prepaid Cards

You can open current account for your customers using:

- Accounts API
- Accounts Dashboard

Currently, we support creating current accounts with our partner banks - ICICI and YES Bank. We are working with Axis Bank and RBL Bank, they will be available soon.

### Create Current Account Using API

The following APIs will help you to create and manage current account for your customers. If a customer account already exists with our partner banks you can easily add it to Cashfree Payments Accounts, you do not have to create a new account for such users.

- [Create Current Account](ref:create-current-bank-account) - Allows you to create a current bank account for your customer.
- [Add Existing Account](ref:add-existing-account) - Allows you to add an existing customer current account with partner bank to Cashfree Payments.
- [Get Customer Instrument](ref:get-customer-instrument) - Allows you to fetch the instrument details of a customer.
- [Get Multiple Customer Instruments](ref:get-customer-instruments) - Allows you to fetch all the instruments issued for a customer.
- [Delete Customer Instrument](ref:delete-customer-instrument) - Allows you to delete a customer's payment instrument.

If you face any errors while creating current account for your customers, check [Payment Instruments Error Codes](ref:payment-instruments-errors) for details.

### Create Current Account Using Dashboard

To create a current account payment instrument,

1. Go to **Accounts Dashboard** > **Payment Instruments**.
2. In the **Current Account** section, click **Add Current Account**.
3. Enter **Customer ID** of the customer you want to create a current account for.
4. In the Instrument Action field:  
   a) Select **Open New Account** to open a new current account for your customer, or  
   b) Select **Add Existing Account** if a current account already exists for your customer and you  
       want to link it to Cashfree Payments now.
5. Enter **Instrument ID**. This is the current account ID that you want to assign for this customer
6. Select the partner bank with whom you want to create the account for your customer. You can choose to create a current account either via ICICI or YES bank.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/87946ce-Screenshot_2022-05-23_at_9.07.03_AM.png",
        "Screenshot 2022-05-23 at 9.07.03 AM.png",
        485
      ],
      "border": true,
      "caption": "Add Current Account - 1"
    }
  ]
}
[/block]


6. Click **Next**. 
7. Enter the customer details as per their KYC document, and the Branch details where you want to open the account. For the branch details, enter the pincode of the residential or business address of the customer.
8. Click **Add Instrument**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b99baa0-Screenshot_2022-05-23_at_9.07.50_AM.png",
        "Screenshot 2022-05-23 at 9.07.50 AM.png",
        490
      ],
      "border": true,
      "caption": "Add Current Account - 2"
    }
  ]
}
[/block]


***

# On-Boarding & KYC Verification Process

The partner bank is notified after you add and submit the details of the customer for opening the current account. The bank begins the onboarding process for the customer.

The bank first reaches out to the customer, post which their offline KYC process is initiated where a field executive does an on-site verification, as mandated by the RBI. The customer must submit a set of documents required for KYC verification as requested by the bank. The checklist for each partner bank is provided at the end of the page.

Please note for ICICI Bank, the onboarding process will only begin once customer completes OTP on the unique ICICI link we provide to you as an API response (Refer to the block diagram below for better understanding.)

The onboarding and KYC flow for ICICI current account customers is shown below:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/31249d7-Screenshot_2022-05-23_at_9.16.42_AM.png",
        "Screenshot 2022-05-23 at 9.16.42 AM.png",
        679
      ],
      "border": true,
      "caption": "ICICI Bank KYC Verification Flow"
    }
  ]
}
[/block]


The onboarding and KYC flow for YES bank current account customers is shown below: 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/11afaa5-Screenshot_2022-05-23_at_9.16.55_AM.png",
        "Screenshot 2022-05-23 at 9.16.55 AM.png",
        679
      ],
      "border": true,
      "caption": "YES Bank KYC Verification Flow"
    }
  ]
}
[/block]


### Account Opening Status

While the onboarding and KYC verification process is ongoing from the partner bank, Cashfree Payments provides you the account opening status through APIs. The following status updates are available:

| Status   | Description                               |
| :------- | :---------------------------------------- |
| PENDING  | Bank API success, offline process pending |
| REJECTED | Rejected by bank                          |
| CANCELED | Canceled by user                          |
| ACTIVE   | Active                                    |
| INACTIVE | Instrument is deleted                     |
| FAILED   | API related technical failure             |

***

# Connected Banking

You can enable connected banking for your customer’s current account with our connected banking APIs

For connected banking flow for ICICI and YES bank, refer Appendix 

### Connect Instrument:

You can connect or disconnect the current account which was created or existing account that was added to your platform, which you can do via the APIs mentioned below:

- [Connect Bank Account](ref:connect-bank-account)
- [Disconnect Bank Account](ref:disconnect-bank-account)

### Fetch Balance

You can enable your customer to know their bank account balance along with the timestamp of when the balance was last updated on using our [Fetch Balance](ref:get-customer-balance)

You know the balance, you must first ensure your account is connected to Cashfree Payments.

### Create and Manage Beneficiary for Payments

You can enable your customer to create, view, delete beneficiary details using the APIs mentioned below:

- [Create Beneficiary](ref:create-beneficiary-1)
- [Get Beneficiary Details](ref:get-beneficiary)
- [Get Multiple Beneficiaries Details](ref:get-beneficiaries)
- [Delete Beneficiary](ref:delete-beneficiary)

Beneficiary error codes - <https://docs.cashfree.com/reference/beneficiary-error-codes>

If you face any errors while creating and managing beneficiaries, check [Beneficiary Error Codes](ref:beneficiary-error-codes) for details.

2.5.4 Make Transfer:  
You can enable your customer to make transfers from their connected current account to beneficiaries they have added using our APIs mentioned below:

- [Request Transfer](ref:request-transfer)
- [Request Direct Transfer](ref:request-direct-transfer)
- [Get Transfer](ref:get-transfer)
- [Get Multiple Transfers](ref:get-transfers)

If you face any errors during transfers, check [Transfer Error Codes](ref:transfer-error-codes) for details.

***

# Reports

The reports section gives you details of all the customers you have added, the payment instruments created and also about the transfers made. These reports can be viewed for a particular period of not more than 30 days and can give you detailed insights to make informed decisions.

To view the reports, 

1. Go to **Account Dashboard** > **Reports**. 
2. Select the type of report you want to view. Reports supported are - Customer, Payment Instruments, and Transfers.
3. Click **Generate**. Select the type fo details you want to view in the report and click **Generate**.

***

### ICICI KYC Checklist 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8ce761c-Screenshot_2022-05-23_at_10.46.00_AM.png",
        "Screenshot 2022-05-23 at 10.46.00 AM.png",
        671
      ],
      "border": true
    }
  ]
}
[/block]


### YES Bank KYC Checklist

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7d7c5d8-Screenshot_2022-05-23_at_2.23.27_PM.png",
        "Screenshot 2022-05-23 at 2.23.27 PM.png",
        679
      ],
      "border": true
    }
  ]
}
[/block]
