---
title: "Create Terminal Transaction"
slug: "create-terminal-transaction"
excerpt: "Use this API to create a new terminal transaction."
hidden: false
createdAt: "Thu Oct 12 2023 13:09:32 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Wed May 29 2024 13:13:54 GMT+0000 (Coordinated Universal Time)"
---
To use this API you should first create an order using the [Create Order](ref:createorder) API. Also, you need to enter the terminal details while creating the order and pass the same terminal information while creating a transaction using the below mentioned API. 

If the `add_invoice` parameter is set to `true`, the generated QR code will include GST information. Otherwise, set it to `false` to generate a normal QR code without GST information.
