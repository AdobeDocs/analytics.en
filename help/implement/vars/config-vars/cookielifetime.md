---
title: cookieLifetime
description: Override the expiration for cookies that AppMeasurement creates.
feature: Appmeasurement Implementation
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/Vnia0RzQf6S5-gbgwIlM0WOiSgm2ZOzL24pvIKNgMl4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# cookieLifetime

Cookies set by AppMeasurement typically have an expiration of 2 years. Use the `cookieLifetime` variable to override the expiration date for cookies set by AppMeasurement.

>[!NOTE]
>
>This variable impacts unique visitor counts and attribution. Use caution when setting this variable.

## Cookie Lifetime using the Web SDK

The Web SDK does not yet offer customization to the lifetime of cookies that it sets.

## Cookie Lifetime using the Adobe Analytics extension

Cookie Lifetime is a drop-down list under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
1. Expand the [!UICONTROL Cookies] accordion, which reveals the [!UICONTROL Cookie Lifetime] drop-down list.

This drop-down list contains the following values:

* **Default**: Cookie expires after 2 years.
* **None**: AppMeasurement does not set cookies.
* **Session**: Cookie expires at the end of the visitor's session.
* **Seconds**: Cookie expires after the specified number of seconds have elapsed. For example, setting this drop-down list to [!UICONTROL Seconds] and placing `86400` into the custom field forces cookies to expire after exactly 24 hours.

## s.cookieLifetime in AppMeasurement and the Analytics extension custom code editor

The `s.cookieLifetime` variable is a string that determines the expiration date of cookies set by AppMeasurement.

* If set to `SESSION`, cookies set by AppMeasurement expire after the browser session completes.
* If set to `NONE`, AppMeasurement does not attempt to set cookies.
* If set to an integer string, cookies set by AppMeasurement expire after the specified number of seconds have elapsed.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
