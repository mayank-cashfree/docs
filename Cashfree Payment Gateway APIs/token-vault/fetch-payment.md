---
title: "Fetch All Saved Card Payment Instruments"
slug: "fetch-payment"
excerpt: "Use this API to get all saved card payment instruments for a customer."
hidden: true
createdAt: "Wed Jan 12 2022 12:52:02 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Wed Jan 12 2022 13:01:25 GMT+0000 (Coordinated Universal Time)"
---
## Response Parameters

| Name               | Type   | Description                                                                                                                                                                                                                                                                        |
| :----------------- | :----- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| instrument_id      | String | The reference id of the saved instrument. Unique for a save instrument request but not unique for a particular instrument like card number or vpa.                                                                                                                                 |
| instrument_type    | String | Type of instrument - card, vpa                                                                                                                                                                                                                                                     |
| instrument_uid     | String | Unique identifier for the instrument. For example, if a same card is saved by 2 different customers the instrument_uid would be same for both the cards                                                                                                                            |
| instrument_display | String | The display text for the saved instrument. For example, in case of saved cards the first 12 digits would be masked and only the last 4 digits would be visible in the instrument display string. It can be displayed to the customer for selecting a saved instrument for payment. |
| card_network       | String | The card network to which the saved card belongs. Visa, Mastercard, Rupay, etc.                                                                                                                                                                                                    |
| card_bank_name     | String | Card issuing bank name                                                                                                                                                                                                                                                             |
| card_country       | String | Card issuing country code                                                                                                                                                                                                                                                          |
| card_type          | String | Debit, credit, prepaid, etc.                                                                                                                                                                                                                                                       |
| token_expiry_month | String | The expiry month of saved card token                                                                                                                                                                                                                                               |
| token_expiry_year  | String | The expiry year of saved card token                                                                                                                                                                                                                                                |
| instrument_status  | String | The status of saved instrument - INACTIVE, ACTIVE, EXPIRED                                                                                                                                                                                                                         |
