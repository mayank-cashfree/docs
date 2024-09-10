---
title: "BaaS Accounts FAQ"
slug: "baas-faq"
excerpt: ""
hidden: true
createdAt: "Wed Aug 03 2022 17:11:42 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Dec 05 2023 13:45:31 GMT+0000 (Coordinated Universal Time)"
---
### How to recharge or top up my BaaS Virtual Account?

Upon creation of a BaaS Virtual Account, you will receive the account number and the IFSC code of the VA in the API response. You can add the VA details as beneficiary on your bank account’s net banking portal and make a transfer using IMPS/NEFT/RTGS. The settlement time depends on the mode of transfer used.

Alternatively, you can integrate Cashfree’s Payment Gateway to create a seamless recharge flow on your platform. However, the default settlement time for Payment Gateway collections is T+1. Instant settlements can also be enabled at an additional cost.

***

### What is the difference between Request Transfer API and Request Direct Transfer API?

Request Transfer API requires you to first create a beneficiary using the [Create Beneficiary](ref:api-create-beneficiary) API. Transfer can be initiated only after the beneficiary has been created. Request Direct Transfer API does not require you to create a beneficiary separately. The beneficiary details can be passed in the request body of the API along with the details of the transfer.

***

### What is the cool-down period for disbursals to newly added beneficiaries?

There is no cool-down period for newly added beneficiaries. Transfers can be made instantaneously.

***

### What are the modes of transfers available for disbursals and what is the individual limit for each of these modes?

- IMPS: Upper Limit - INR 2 Lakhs
- NEFT: Upper Limit - INR 10 Lakhs
- RTGS: Limit -  min. INR 2 Lakhs, no upper limit
- UPI: Upper Limit - INR 1 Lakh	

***

### What is the difference between a BaaS merchant VA and a BaaS customer VA? 

The BaaS merchant VA is a VA created for you to provide flexibility such as transaction based settlement to your customer. You can transfer money from the merchant VA to a customer VA, but you cannot transfer money from a customer VA to a customer VA, or a customer VA to a merchant VA. To create a BaaS merchant VA, choose the customer type as ‘Internal’. You can use the Internal Transfer API to enable transfers from Merchant VA to Customer VA.

***

### How can I create a BaaS Merchant Virtual Account?

First, a customer must be created using our [Create Customer](ref:customers) API by entering merchant’s details. The customer type for this merchant is to be set as ‘INTERNAL’.  
Once the customer is created, a virtual account can be created for this customer using the [Create BaaS Virtual Account](ref:create-virtual-account) API. This VA will act as the BaaS Merchant Virtual Account.

***

### How can I transfer money from the BaaS Merchant Virtual Account to a BaaS Customer Virtual Account?

You can transfer money from the BaaS Merchant Virtual Account to a BaaS Customer Virtual Account using the BaaS [Internal Transfer](ref:baas-internal-transfer) API.

***

### Can I create a VPA for each BaaS Virtual Account?

The feature is under development. Will be available soon.

***

### What BaaS functionalities are available on the merchant dashboard? 

You can create Customers and Virtual Accounts for those customers on the merchant dashboard. Additionally, you can view reports of customers and VAs created as well as transfers made using the VAs. All other functionalities such as disbursals, VA statements, beneficiary creation etc. are only available via APIs.

***

### What is the KYC required from my customer? 

The KYC requirements can vary depending on the use case & also the customer type. Contact your account manager to know more.

***

### How can I access BaaS from the merchant dashboard?

Select the ‘Accounts’ Tile from the merchant dashboard home screen. You can toggle between Test and Production environments by clicking on the ‘Switch to Test’ and ‘Switch to Production’ buttons on the top right corner.

***

### How do I obtain API Keys (client ID and client secret) for BaaS? 

The Client ID and Client Secret API Keys can be obtained from the merchant dashboard. Please refer to [this](https://docs.google.com/document/d/1R6oy27wHf4l5sZK5RKhFBl0sUZTPH6bmvjZ0Yf-eK84/edit) document for detailed instructions.

***

### What is the ‘cf-api-version’ field in the header section of the API request?

cf-api-version needs to be passed as the value as the current date in the format yyyy-mm-dd.

***

### How to create BaaS Virtual Accounts for customers?

First, a customer needs to be created using the [Create Customer](ref:customers) API. Once a customer has been created, BaaS Virtual Accounts can be created for the customer using the [Create BaaS Virtual Account](ref:ref:create-virtual-account) API. The customer_id of the customer for whom the VA is being created needs to be passed in the request body of the Create BaaS Virtual Account API. The response of this API will contain the account number and IFSC code of the newly created BaaS VA.

***

### What is the ‘customer_id’ field?

The customer_id field is a unique reference ID that you can set for each customer that you create. Maximum of 50 alphanumeric characters, special characters - comma, underscore, and hyphen are allowed.

***

### What is the ‘instrument_id’ field?

The instrument_id field is a unique reference ID that you can set for each BaaS virtual account that you create for your customers. Maximum of 50 alphanumeric characters, special characters - comma, underscore, and hyphen are allowed.

***

### What are the endpoints to be used for API requests in UAT and Production?

- **Sandbox/UAT**: <https://test.cashfree.com/banking>
- **Production**: <https://api.cashfree.com/banking>

***

### How can I configure webhooks?

Webhooks can be configured on the merchant dashboard via the **Developers** section. Please refer to [this](https://docs.google.com/document/d/1stqg8J8xCJw2H0NqLDxDwQ2bnduptIMSAxkgDr36CmM/edit) document for detailed instructions.

***

### How can I whitelist my IP address for BaaS APIs?

You can whitelist your IP address for BaaS APIs on the merchant dashboard via the Developers section. Please refer to [this](https://docs.google.com/document/d/1xfCpAU74qZ9fqmJ88y_bK7yjwulNqAptt9-8iTJDk0w/edit) document for detailed instructions.

***
