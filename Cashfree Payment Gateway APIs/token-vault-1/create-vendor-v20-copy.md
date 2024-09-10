---
title: "Create Vendor v2.0 (COPY)"
slug: "create-vendor-v20-copy"
excerpt: "Use this API to create a new vendor to your EasySplit account along with the KYC details. Provide KYC details such as account_type, business_type, gst, cin, pan, passport number and so on. Click [here](doc:vendor-kyc) to read more on vendor KYC."
hidden: true
createdAt: "Thu Oct 12 2023 13:09:15 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Thu Oct 12 2023 13:09:15 GMT+0000 (Coordinated Universal Time)"
---
For Auto Collect pass the Authorization token. Use the [Authorize API](ref:authorize-es) to generate the token for Auto Collect APIs.

> 📘 Vendor Instant Settlements
> 
> Use schedule option "8" or "9" to schedule instant settlements to your vendor account.

</details>

<details>
<summary>Schedule Options Supported</summary>

### Schedule Options

| ID | Description                                                                                                          |
| :- | :------------------------------------------------------------------------------------------------------------------- |
| 1  | T+1 settlement at 11:00 AM                                                                                           |
| 2  | T+2 settlement at 11:00 AM                                                                                           |
| 3  | All transactions from 4:30 PM T-1 to 10:30 AM T+0 settled at 11AM T+0, and, 10:30 AM T+0 to 4:30PM T+0 at 5:00PM T+0 |
| 4  | All transactions from 2:00 PM T-1 to 2:00 PM T+0 settled at 3PM T+0                                                  |
| 5  | All transactions till 5.30 at 6                                                                                      |
| 6  | Instant Settlement Every Hour between 7:00 AM and 5:00 PM on working days                                            |
| 7  | Instant Settlement Every 3 hours between 8:00 AM and 5:00 PM on working days                                         |
| 8  | Instant Settlement Every Hour 24\*7                                                                                  |
| 9  | Instant Settlement Every 3 Hours 24\*7                                                                               |
| 11 | Weekly Every 1st Working day                                                                                         |
| 12 | Monthly Every 1st Working day                                                                                        |

***

</details>

<details>
<summary>List of Business Types</summary>

| Business Types                                                                     |
| :--------------------------------------------------------------------------------- |
| Government                                                                         |
| Insurance                                                                          |
| Jewellery                                                                          |
| Gemstone/Diamond                                                                   |
| Mutual funds/Broking                                                               |
| NBFCs / Organizations into Lending                                                 |
| Non Profit / NGO                                                                   |
| Online Gaming                                                                      |
| Open/Partial Open Wallet                                                           |
| Pharmacy                                                                           |
| Travel and Hospitality                                                             |
| Utilities                                                                          |
| Aggregators                                                                        |
| Hemp Products / Herbal Products                                                    |
| FOREX                                                                              |
| Chit Funds                                                                         |
| Web host/Domain seller                                                             |
| Professional Services (Doctors, Lawyers, Architects, CAs, and other Professionals) |
| Food Industry                                                                      |
| International Card Acceptance (Goods export)                                       |

***

</details>

<details>
  <summary>Response Codes
</summary>

| Sub Code | Status | Message                             | Solution                                                                                              |
| :------- | :----- | :---------------------------------- | :---------------------------------------------------------------------------------------------------- |
| 400      | ERROR  | vendor_id_invalid                   | Specify a valid alphanumeric vendor ID.                                                               |
| 400      | ERROR  | status_invalid                      | Provide a valid status. Possible values are: ACTIVE or BLOCKED.                                       |
| 400      | ERROR  | Invalid Name                        | Provide a valid name. The name should not have any special character except. / - &,                   |
| 400      | ERROR  | Invalid Name                        | Provide a valid name. Ensure the name size must be between 0 and 100.                                 |
| 400      | ERROR  | Invalid email ID                    | Specify a valid Email ID.                                                                             |
| 400      | ERROR  | Email ID not specified              | Specify a valid Email ID.                                                                             |
| 400      | ERROR  | Phone number not specified          | Specify a valid phone number.                                                                         |
| 400      | ERROR  | Please provide a valid Phone number | Specify a valid phone number without special characters and the length is 10 digits.                  |
| 400      | ERROR  | VPA not specified                   | Specify a valid VPA                                                                                   |
| 500      | ERROR  | Failed to validate VPA              | Retry after sometime                                                                                  |
| 400      | ERROR  | Account holder name not specified   | Specify a valid account holder name                                                                   |
| 400      | ERROR  | Invalid account holder name         | Specify an account number without any special characters except. / - &,                               |
| 400      | ERROR  | Invalid account type                | Provide a valid account type without any special characters. Possible values: BUSINESS or INDIVIDUAL. |
| 400      | ERROR  | Invalid uidai number                | Provide a valid uidai (Aadhaar) number without special characters and the length is 12 digits.        |
| 400      | ERROR  | Invalid gst number                  | Provide a valid GST number without special characters and the length is 15 digits.                    |
| 400      | ERROR  | Invalid cin                         | Provide a valid CIN number without special characters and the length is 21 digits.                    |
| 400      | ERROR  | Invalid PAN                         | Provide a valid PAN number without special characters and the length is 10 digits.                    |
| 400      | ERROR  | Invalid passport number             | Provide a valid passport number without any special characters and the length is 8 digits.            |
| 400      | ERROR  | Merchant is not Active              | Ensure merchant status is Active                                                                      |

***

</details>
<details>
  <summary>Sample bank account numbers and upi vpas to test the API in the test environment.
</summary>

## Bank Numbers

For banks, the primary parameters for transfer would be the bank account and IFSC number included while adding the vendor. Sample details shared below are to simulate different vendor settlement situations.  

| Name     | Account Number  | IFSC        | Remarks                                       |
| :------- | :-------------- | :---------- | :-------------------------------------------- |
| John Doe | 026291800001191 | YESB0000262 | Success                                       |
| John Doe | 00011020001772  | HDFC0000001 | Success                                       |
| John Doe | 000890289871772 | SCBL0036078 | Success                                       |
| John Doe | 000100289877623 | SBIN0008752 | Failed at bank                                |
| John Doe | 2640101002729   | CNRR0002640 | Failure – Invaid IFSC code                    |
| John Doe | 026291800001190 | YESB0000262 | Failure – Invalid Account number              |
| John Doe | 02014457596969  | CITI0000001 | Success (later to Reversed)                   |
| Jon D    | 026291800001191 | YESB0000262 | Failure - Account holder name matching failed |

***

## UPI

For UPI, the primary parameter for transfer would be the UPI VPA included while adding the vendor. Use these UPI VPA to test transfers to the vendor account.

| VPA                           | Remarks                 |
| :---------------------------- | :---------------------- |
| success@upi                   | Successful UPI transfer |
| incorrect@upi and invalid@upi | Failed UPI transfer     |

***

</details>

Watch this video to learn how to add a new vendor via API

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2F_Vde5QDJwg8%3Ffeature%3Doembed%26start%3D198%26end%3D235&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D_Vde5QDJwg8&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2F_Vde5QDJwg8%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/embed/_Vde5QDJwg8?start=198&end=235",
  "title": "Easy Split by Cashfree Payments | 2-step integration to split incoming payments",
  "favicon": "https://www.youtube.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/_Vde5QDJwg8/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/embed/_Vde5QDJwg8?start=198&end=235"
}
[/block]
