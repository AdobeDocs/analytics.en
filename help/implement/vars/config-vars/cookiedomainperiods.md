---
title: cookieDomainPeriods
description: (Deprecated) Help AppMeasurement determine where to store cookies when a website's top-level domain contains a period.
feature: Appmeasurement Implementation
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/bsJTIAuqcWoXWWus0oPME9LEwEMaiCGjd1ChmCuSjKY'
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# cookieDomainPeriods

>[!IMPORTANT]
>This variable is deprecated. If you use any of the following:
>
>* AppMeasurement v2.26.x or later
>* Adobe Analytics extension v1.9.4 or later
>* Adobe Experience Cloud ID service
>
>This variable does nothing, as the applicable library automatically detects the domain to set cookies on.

The `cookieDomainPeriods` variable helped AppMeasurement determine where to set Analytics cookies by indicating that the top-level domain had an extra period in it. This variable allowed AppMeasurement to accommodate the extra period in the top-level domain and set cookies in the correct location. If your website's top-level domain does not include an extra period, this variable is not required.

* For domains like `example.co.uk` or `www.example.co.jp`, set this variable to `"3"`.
* For domains like `example.nsw.gov.au`, set this variable to `"4"`.
* For domains like `example.com` or `products.example.org`, omit setting this variable or set it to `"2"`.

>[!TIP]
>
>Do not take subdomains into account for this variable. For example, do not set `cookieDomainPeriods` on the example URL `store.toys.example.com`. AppMeasurement recognizes that cookies are stored on `example.com`, even on URLs with many subdomains.

For implementations on AppMeasurement v2.26.x or later, the [`s_ac`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie is used to help automatically determine the correct cookie domain. The library first attempts to write a cookie including two domain periods. If setting this cookie fails, it tries again, including more domain periods until it succeeds. This cookie is immediately deleted once set.

## Cookie domain periods using the Web SDK

The Web SDK automatically determines the correct domain to set cookies.

## Cookie domain periods using the Adobe Analytics extension

**[!UICONTROL Domain Periods]** is a field under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
1. Expand the [!UICONTROL Cookies] accordion, which reveals the [!UICONTROL Domain Periods] field.

Set this field to `3` only on top-level domains that contain a period. Otherwise, this field can be left blank.

## Cookie domain periods in AppMeasurement and the Analytics extension custom code editor

The `cookieDomainPeriods` variable is a string that is typically set to `"3"`, only on top-level domains that contain a period. Its default value is `"2"`, which accommodates most top-level domains like `.com` and `.org`.

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
