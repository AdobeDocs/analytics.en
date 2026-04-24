---
title: cookieDomain
description: (Retired) Helps determine the domain to set cookies on.
feature: Appmeasurement Implementation
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
role: Admin, Developer
TQID: https://experienceleague.adobe.com/z6occeGLpxezOj7go2DrwG-j-fc9yBuGyHSmZJK9RfQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
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
---
# cookieDomain

>[!IMPORTANT]
>This variable is retired. Use [`trackingServer`](trackingserver.md) instead.

The `cookieDomain` variable determines the domain where AppMeasurement sets cookies. You can use this variable to explicitly set the cookie domain instead of using the [`cookieDomainPeriods`](cookiedomainperiods.md) variable.

This variable only needs to be used when **both** of the following conditions are met:

* If your implementation uses first-party cookies. This variable is not required with implementations using a [`trackingServer`](trackingserver.md) value containing `sc.adobedc.net`.
* If your domain has a period in its suffix. For example, `example.co.uk` could use the `cookieDomain` variable to explicitly state that the cookie domain is `example.co.uk` and not `co.uk`.

Only a small number of implementations have use for the `cookieDomain` variable, and even then, alternative variables like [`cookieDomainPeriods`](cookiedomainperiods.md) can be used instead.

## Cookie Domain using the Web SDK

The Web SDK can determine the correct cookie storage domain without this variable.

## Cookie Domain using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.cookieDomain in AppMeasurement and the Analytics extension custom code editor

The `cookieDomain` variable is a string, and is set to the domain that you want to store cookies on.

```js
s.cookieDomain = "stats.example.com";
```
