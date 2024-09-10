---
title: "Analytics"
slug: "webhook-analytics"
excerpt: ""
hidden: true
createdAt: "Tue Feb 07 2023 10:55:33 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Feb 07 2023 10:55:33 GMT+0000 (Coordinated Universal Time)"
---
The webhook logs and analytics feature helps you to easily integrate with Cashfree Payments webhooks by providing contextual information on webhook delivery on Cashfree Payments dashboard. 

## Configuration

Add and define individual webhooks for products under Payment Gateway, and get notified for each action on the URLs configured.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/317df88-Configuration.png",
        "Configuration.png",
        3456
      ],
      "sizing": "smart",
      "border": true,
      "caption": "Configuration"
    }
  ]
}
[/block]


**Adding a Webhook URL **

To add a new webhook, 

1. Go to Payment Gateway Dashboard > in the left navigation bar, and select **Developers**. 
2. Click the **Add Webhook URL** option to create a new webhook. 
3. Configure the webhook type: Payment Success/Payment Failed/User Dropped. 
4. Configure the API version: 2021-09-21 or 2022-09-01. Enter the webhook URL and click **Test & Add**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b09f5e1-Screenshot_2023-02-07_at_3.54.14_PM.png",
        "Screenshot 2023-02-07 at 3.54.14 PM.png",
        3456
      ],
      "sizing": "smart",
      "border": true,
      "caption": "Add webhook URL"
    }
  ]
}
[/block]


5. Review your selections and click on **Add**. The webhook is created successfully. It can be enabled or disabled from the Configuration page. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/29abb91-Screenshot_2023-02-07_at_3.56.01_PM.png",
        "Screenshot 2023-02-07 at 3.56.01 PM.png",
        1336
      ],
      "sizing": "smart",
      "border": true,
      "caption": "Review Selections"
    }
  ]
}
[/block]


## Logs

View logs of success/failed webhooks on your dashboard. Specify the date range to view logs for a particular period. You also have the option to search and filter for the required logs. Enter the URL and select the required webhook type from the list. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4573545-Logs.png",
        "Logs.png",
        3456
      ],
      "sizing": "smart",
      "border": true,
      "caption": "Logs"
    }
  ]
}
[/block]


Click on a particular request to view more details such as message, time, version, header details, and the payload. If you want to view logs of success or failed alone navigate to the respective pages.  

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b3a34c7-Screenshot_2023-02-07_at_3.29.02_PM.png",
        "Screenshot 2023-02-07 at 3.29.02 PM.png",
        3456
      ],
      "sizing": "smart",
      "border": true,
      "caption": "Logs - Expanded Details"
    }
  ]
}
[/block]


## Analytics

The analytics section consists of the webhook metrics that allow you to track, monitor and assess the success or failure of your webhooks. Metrics such as Error Counts and Latency are available. 

Specify the date range to view the metrics for a particular period. You also have the option to search and filter for the required webhook. Enter the URL and select the required webhook type from the list. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6295a8b-Screenshot_2023-02-07_at_3.43.43_PM.png",
        "Screenshot 2023-02-07 at 3.43.43 PM.png",
        3456
      ],
      "sizing": "smart",
      "border": true,
      "caption": "Search and Filter"
    }
  ]
}
[/block]


**Error Count**

The error count is the count of the different errors received when sending webhooks. Details such as Total Success Count and Total Failed Count are displayed. Hover your mouse over the individual date to view the failedCount. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/be5411a-Screenshot_2023-02-07_at_3.39.58_PM.png",
        "Screenshot 2023-02-07 at 3.39.58 PM.png",
        3456
      ],
      "sizing": "smart",
      "border": true,
      "caption": "Analytics"
    }
  ]
}
[/block]


  **Latency**  
Latency is the time taken to respond to webhooks. Hover your mouse over the individual date to view the latency count. The average latency value is also provided. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2e5c208-Screenshot_2023-02-07_at_3.48.32_PM.png",
        "Screenshot 2023-02-07 at 3.48.32 PM.png",
        3456
      ],
      "sizing": "smart",
      "border": true,
      "caption": "Latency"
    }
  ]
}
[/block]


## Service Alerts

The service alerts section allows you to:

- Activate or deactivate a webhook
- Configure webhook URL

To configure the webhook URL,

1. Go to Payment Gateway Dashboard > in the left navigation bar, and select **Developers**.
2. In the Developers screen, go to the Service Alerts section and click **Add Webhook URL** and specify a valid webhook URL. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8ff6387-Screenshot_2023-02-07_at_4.21.03_PM.png",
        "Screenshot 2023-02-07 at 4.21.03 PM.png",
        3456
      ],
      "sizing": "smart",
      "border": true,
      "caption": "Add Webhook URL"
    }
  ]
}
[/block]


4. Click **Test & Add** to save the webhook URL. Review your selections and click **Add**. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/24a16da-Screenshot_2023-02-07_at_4.22.21_PM.png",
        "Screenshot 2023-02-07 at 4.22.21 PM.png",
        3456
      ],
      "sizing": "smart",
      "border": true,
      "caption": "Review webhook URL"
    }
  ]
}
[/block]
