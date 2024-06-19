---
title: cookieDomainPeriods
description: Help AppMeasurement understand what domain to store cookies if your domain has a period in its suffix.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
---

# cookieDomainPeriods

>[!IMPORTANT]
>This variable is deprecated. If you use AppMeasurement v2.26.x or later, or the Adobe Analytics extension v1.9.4 or later, the library automatically detects the domain to set cookies on.

The `cookieDomainPeriods` variable helped AppMeasurement determine where to set Analytics cookies by indicating that the top-level domain had an extra period in it. This variable allowed AppMeasurement to accommodate the extra period in the top-level domain and set cookies in the correct location. If your website's top-level domain does not include an extra period (like `example.co.uk`), this variable is not required.

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

## Cookie domain periods in code AppMeasurement and the Analytics extension custom code editor

The `cookieDomainPeriods` variable is a string that is typically set to `"3"`, only on top-level domains that contain a period. Its default value is `"2"`, which accommodates most top-level domains like `.com` and `.org`.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
