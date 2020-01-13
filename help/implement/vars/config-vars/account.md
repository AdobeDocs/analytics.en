---
title: account
description: Use the account variable to determine the report suite where data is sent to.
---

# account

The `account` variable determines the report suite you want to send data to. A report suite ID is required to send data to Adobe Analytics.

If you use the `s_gi()` function to instantiate an Analytics tracking object, the report suite ID's already exist as a required argument in the function. If using the `s_gi()` function, setting `account` is not required.

## Report Suites in Adobe Experience Platform Launch

Report Suites are three fields under the [!UICONTROL Library Management] accordion when configuring the Adobe Analytics extension. These fields are required for data collection in Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Library Management] accordion, which reveals the [!UICONTROL Report Suites] fields.

Enter the Development Report Suites, Staging Report Suites, and Production Report Suites in each respective field. Valid contents for each field is a report suite ID, or multiple report suite ID's delimited by a comma.

## s.account in AppMeasurement and Launch custom code editor

The `s.account` variable is a string containing a report suite ID or multiple report suite ID's delimited by a comma. Do not include spaces in this variable.

If instantiating the Analytics tracking object using `s_gi()`, report suite ID's are already included as an argument to the function. In these cases, also setting report suite ID(s) in `s.account` is not required. Only use `s.account` if you want to change the report suite(s) AppMeasurement sends an image request to.

```js
// Send data to a single report suite
s.account = "examplersid";

// Send data to multiple report suites
s.account = "examplersid1,examplersid2,examplersid3";
```
