---
title: "BaaS Prepaid Card Issuance"
slug: "ppi-card"
excerpt: ""
hidden: true
createdAt: "Sun Sep 25 2022 17:57:11 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Dec 05 2023 13:45:30 GMT+0000 (Coordinated Universal Time)"
---
Cashfree Payments provides an end-to-end solution for PPI card issuance, starting from setting up the program, onboarding customers, and also issuing cards based on minimum and full KYC verification. Businesses can use either the Cashfree merchant dashboard or the PPI card issuing API stack for various card-related operations.

Using the Cashfree Payments BaaS PPI card issuing stack, the end customers can access their cards as any prepaid instrument. They can load money into the card, check statements and use the funds for various expenses as defined under the program.

# Benefits - PPI Card Issuance

The PPI card can have multiple use cases like gift cards, loyalty cards, expense management, financial planning, neobanking, etc. Our PPI card issuing stack provides a program for both open and closed loops. Owning a program helps the merchant in the following ways:

- **Better brand visibility**: With co-branded cards, one can improve their visibility
- **Visibility and control**: Control spending & limit allocation
- **Secure & Reliable**: Enable expenses, salary disbursals, credit & other use cases in a secure & reliable set-up
- **DIY**: Design your own card and program
- **Flexibility in form factor**: Choose from physical or virtual cards or enable the program on a wearable like watches and keys.

# Payment Modes Supported

The end customer can transact on different platforms using various payment modes like **POS**, **cash withdrawal**, and **online transactions**. It helps businesses to generate revenue when your customers transact using PPI card.

# Customise Card Program

Businesses can integrate with our PPI card issuing stack hassle-free and can avoid multiple integrations with various parties like issuer, switch, network, and printing vendor. For the creation of the program, you need to finalise the following based on the branding of the card:

**Mono-branded cards - Branded on the name of the issuer**

- Network- VISA, RuPay
- Issuing banks- Yes Bank, SBM, NSDL
- Type of card- Physical, Digital, 
- Card limit- up to 2 lakhs
- Type of KYC- min KYC, full KYC
- Type of transaction- POS, Cash Withdrawal, online transaction

**Co-branded cards - Branded on the name of the merchant and the issuer**

- Network- VISA, RuPay
- Issuing banks- Yes Bank, SBM, NSDL
- Type of card- Physical, Digital, 
- Card limit- up to 2 lakhs
- Type of KYC- min KYC, full KYC
- Type of transaction- POS, Cash Withdrawal, online transaction
- Design of Card

Once the program is finalised and approved by the issuer. The BIN gets allocated for the co-branded and the merchant gets created on the Cashfree dashboard. The merchant can parallelly finalise the card and stationery designs for the program that will be used to onboard their customers.

Cashfree Payments provides a dashboard where you can have complete visibility of the program once it is approved. On the dashboard, you can create new customers, issue cards, and check the status and balances of their customers. You can also deactivate the cards as per their program.

**API Workflow** 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/50b9a50-Screenshot_2022-09-25_at_11.32.32_PM.png",
        "Screenshot 2022-09-25 at 11.32.32 PM.png",
        903
      ],
      "border": true,
      "caption": "API Workflow"
    }
  ]
}
[/block]


# Create Merchant and Card Program 

Merchants will be created in Cashfree Payments production dashboard once the program is finalised and approved by the issuing bank. Once the merchant is live on the dashboard, the merchant can use the Cashfree Payments dashboard as well as APIs to create customers and issue cards.

## Create Customers

You can add customer details using: 

- [Accounts APIs](doc:add-customer-details-using-api)
- [Accounts Dashboard](doc:add-customer-details-using-product-dashboard)

### Add Customer Details Using API

The following APIs will help you to create, edit, and delete customer details.

- **[Create Customer](ref:customers)**- Allows you to create a customer. 
- **[Get customer details](ref:get-customer)**- Allows you to fetch and view customer details of a specific customer.
- **[Get multiple customer details](ref:get-customers)**- Allows you to fetch and view customer details of multiple customers at the same time.
- **[Edit Customer Details](ref:edit-customer)**- Allows you to edit existing customer details like customer type, full name, email address and phone number.

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


## Create and Manage PPI Card

The following APIs will help you to create and manage PPI for your customers. Once the customer is created, PPI card can be issued to the customer using the following APIs.

Pre Requisites: 

- **[Common API Authentication](ref:api-authentication)**

- **[Common Error Handling](ref:error-handling)**

- **[Create Prepaid Card](ref:create-prepaid-card)** – Allows you to create a card.

- **[Generate OTP](ref:generate-otp)** – Allows you to generate OTP for the customer.

- **[Validate OTP](ref:validate-otp)** – Allows you to Valid OTP for verifying the customer.

- **[Minimum KYC](ref:min-kyc)** – Allows you to do minimum KYC to activate the card.

- **[Get Instrument](ref:get-instrument) ** – Allows you to fetch and view data of an instrument.

- **[Get Instruments](ref:get-instruments) ** – Allows you to fetch and view data of multiple instruments.

- **[Edit Card](ref:edit-card)** – Allows you to edit card details.

Once the card is activated, the customer can do the transaction using the card. The merchant can check balances and load cards using the following APIs.

- **[Get Balance](ref:get-balance-1)** – Allows you to fetch the balance.
- **[Add Amount to Card](ref:add-amount-to-card)** – Allows you to add required amount to the card.
