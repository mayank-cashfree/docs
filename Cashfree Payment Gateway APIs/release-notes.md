---
title: "Release Notes: V4 (2023-08-01)"
slug: "release-notes"
excerpt: "Changes and Improvements made in the version V4"
hidden: false
createdAt: "Tue Jan 30 2024 10:45:43 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Jan 30 2024 13:39:48 GMT+0000 (Coordinated Universal Time)"
---
Following are the key changes made in the version 2023-08-01 (V4).

1. **New header in API Response**  
   New header "x-deprecated-at" is added in the API response which will let you know the date when the used version is going to get deprecated. 
2. **Cashfree IDs type change**  [BREAKING]  
   All cashfree IDs like `cf_order_id`, `cf_payment_id`, `cf_refund_id` etc are now in **string** format instead of **integer** (in older versions).
3. **Order Entity Changes**
   1. We have removed payments, refunds, settlements urls from order entity. 
   2. `customer_uid` part of customer_details in order entity. This is the unique identifier of the customer created at Cashfree. You can create customer at cashfree using [Create Customer API](https://docs.cashfree.com/v4/reference/pgcreatecustomer)
   3. `order_status` can have two more values - "TERMINATED" and "TERMINATION_REQUESTED". Find the complete list of order statuses [here](https://docs.cashfree.com/v4/docs/transaction-lifecycle#order-state-details)
   4. No longer support for `notify_url` in Create Order API. You can [configure webhooks](https://docs.cashfree.com/v4/docs/configure-webhooks) from dashboard instead.
4. **New Order Termination API **  
   We have released a new API to terminate an Order. Find API details - [Order Termination API.](https://docs.cashfree.com/v4/reference/pgterminateorder)
5. **New Customer APIs**  
   We have released Customer APIs to let merchants create and manager their customers. Find more about this here - [Customer Management](https://docs.cashfree.com/v4/reference/pgcreatecustomer)
6. **New SPOS APIs**  
   Find newly released [SPOS APIs](https://docs.cashfree.com/v4/reference/create-terminal-transaction)
7. **CF Refund IDs**  
   Earlier cf_refund_id used to start with a prefix "refund_" . In this version, you will not get that prefix and cf_refund_id will be directly be the id without any prefix. Example - OLD cf_refund_id = "refund_41805719" , NEW cf_refund_id = "41805719"

## Try out the new version

[block:html]{"html":"<div class=\"labs-callout\">\n    <div class=\"labs-text\">\n      <img class=\"labs-icon\" src=\"https://cashfreelogo.cashfree.com/assets_images/pg/devstudio.svg\" alt=\"labs icon\">\n      Try Cashfree DevStudio\n    </div>\n    <a href=\"https://www.cashfree.com/devstudio\" target=\"_blank\" class=\"labs-btn\">\n      Try Now\n    </a>\n  </div>\n  <link rel=\"preconnect\" href=\"https://fonts.googleapis.com\">\n<link rel=\"preconnect\" href=\"https://fonts.gstatic.com\" crossorigin>\n<link href=\"https://fonts.googleapis.com/css2?family=Inconsolata&display=swap\" rel=\"stylesheet\">\n  <style>\n      .labs-callout{\n          border: 2px solid #141414;\n          border-radius: 8px;\n          padding: 10px;\n          display: flex;\n          justify-content: space-between;\n          font-weight: 500;\n          background-color: #F6FFF1;\n      }\n      .labs-text{\n          display: flex;\n          align-items: center;\n          font-family: 'Inconsolata', monospace;\n        \tcolor: #141414;\n        \tfont-weight: 400;\n        \tfont-size: 16px;\n        \tline-height: 24px;\n      }\n      .labs-icon{\n          width: 115px;\n      }\n      .labs-btn{\n          background-color: #FBB016;\n          color: #141414 !important;\n          border: 2px solid #141414;\n          padding: 8px;\n          border-radius: 8px;\n          display: flex;\n          justify-content: center;\n          align-items: center;\n          text-decoration: none !important;\n      }\n  </style>"}[/block]

***

## Subscribe To Developer Updates

[block:embed]{"html":false,"url":"https://www.cashfree.com/devstudio/preview/pg/embed/devEmail","provider":"cashfree.com","href":"https://www.cashfree.com/devstudio/preview/pg/embed/devEmail","typeOfEmbed":"iframe","height":"60px","width":"100%","iframe":true}[/block]
