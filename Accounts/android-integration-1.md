---
title: "Android Integration"
slug: "android-integration-1"
excerpt: ""
hidden: true
createdAt: "Fri Nov 04 2022 06:19:15 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Dec 05 2023 13:45:31 GMT+0000 (Coordinated Universal Time)"
---
Purpose of this document is to illustrate the method to integrate a cashfree card SDK to any android native application written in Kotlin & Java.  
This library allows developers to add the Card SDK component into their layout as per design. 

Our Android SDK supports **Android SDK version 21 and above** and currently support two features.

- Card Details
- Reset Atm Pin  
  <br/>

**SDK Specification**

|                           |               |
| :------------------------ | :------------ |
| **Platform**              | Android       |
| **Language Supported**    | Kotlin & Java |
| **Min SDK**               | 21            |
| **Target & Compile SDK**  | 32            |

<br/>
Android Permission on Manifest

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

<br/>

**Gradle Dependencies** 

```groovy
implementation 'androidx.core:core-ktx:1.9.0'
implementation 'androidx.appcompat:appcompat:1.5.1'
implementation 'com.google.android.material:material:1.6.1'
implementation 'androidx.constraintlayout:constraintlayout:2.1.4'
```

<br/>
The integration can be completed in a few steps.

1. Getting the SDK.
2. Add Cashfree CardView in your layout XML file.
3. Get the instance of the added Cashfree CardView  onto your activity or fragment. 
4. Init Card and pass required card params.
5. Add Callback for card related events.
