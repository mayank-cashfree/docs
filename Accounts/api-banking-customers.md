---
title: "Create and Manage Customers"
slug: "api-banking-customers"
excerpt: ""
hidden: true
createdAt: "Tue Aug 03 2021 05:24:44 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Dec 05 2023 13:45:31 GMT+0000 (Coordinated Universal Time)"
---
Cashfree APIs and an easy to use dashboard allow you as a merchant to cater to the banking needs of your customers by issuing them different payment instruments. Customers here are referred to as your business customers.

In this section, we will understand how to create, edit, view or delete customers on the Cashfree Payments platform.

# Add Customers

To create payment instruments for your customers you need to first add the customer by specifying their details.

To add a new customer, 

- Navigate to the Customers tab using the left-hand navigation.
- Click **Add Customer** on the top right of the dashboard.
- Enter the required details along with a unique identifier for the customer.

Note: The unique identifier will be subsequently used to perform operations for this customer like issuing payment instruments.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c5b2b0d-Screenshot_2021-08-16_at_9.25.43_PM.png",
        "Screenshot 2021-08-16 at 9.25.43 PM.png",
        3584
      ],
      "sizing": "100",
      "border": true,
      "caption": "Customers"
    }
  ]
}
[/block]


> 📘 Type of Customers
> 
> Cashfree currently supports two type of customer namely - 
> 
> - Individual
> - Proprietorship
> - Partnership
> - Private Limited.
> - Public Limited
> - LLP
> - HUF
> - OPC  
>   You are required to categorise your business customers accordingly. This is required for regulatory requirements and applicability of subsequent functions like issuance of specific payment instrument is governed by the type of the customer.
> 
> Reach out to our payment experts for more information.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fdd7479-Screenshot_2021-08-16_at_9.27.01_PM.png",
        "Screenshot 2021-08-16 at 9.27.01 PM.png",
        3584
      ],
      "sizing": "100",
      "border": true,
      "caption": "Add Customer"
    }
  ]
}
[/block]


## View Customers

You can view the details of your customers or the payments instrument associated with them. To do so, either click on a customer on the customers page, you can use our filters to navigate to the desired customer.

This can help you debug or answer your customers queries with ease. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f5add90-Screenshot_2021-08-17_at_9.12.21_AM.png",
        "Screenshot 2021-08-17 at 9.12.21 AM.png",
        3584
      ],
      "sizing": "100",
      "border": true,
      "caption": "Customer page with instrument details"
    }
  ]
}
[/block]


## Adding a customer using APIs

In addition to the Cashfree dashboard, you can also opt to integrate with our RESTful APIs and automate your business needs. This is more suited for a higher scale and requires development effort at your end.

Explore our [API reference](ref:customers) to know more about the Customer APIs.
