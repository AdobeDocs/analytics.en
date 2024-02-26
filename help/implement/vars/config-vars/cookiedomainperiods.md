---
title: cookieDomainPeriods
description: Help AppMeasurement understand what domain to store cookies if your domain has a period in its suffix.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
---

# cookieDomainPeriods

AppMeasurement determines its cookie location by looking at the domain and domain suffix. For domains like `example.com`, AppMeasurement sets cookies in the correct location. However, for other domains like `example.co.uk`, AppMeasurement can mistakenly set cookies on `co.uk`. Most browsers reject cookies set on this invalid domain, causing issues with visitor identification.

The `cookieDomainPeriods` variable helps AppMeasurement determine where Analytics cookies are set by calling out that the domain suffix has an extra period in it. This variable allows AppMeasurement to accommodate the extra period in the domain suffix and set cookies in the right location.

* For domains like `example.com` or `www.example.com`, this variable does not need to be set. If needed, you can set this variable to `"2"`.
* For domains like `example.co.uk` or `www.example.co.jp`, set this variable to `3`.


>[!IMPORTANT]
>
>Do not take subdomains into account for this variable. For example, do not set `cookieDomainPeriods` on the example URL `store.toys.example.com`. AppMeasurement by default recognizes that cookies should be stored on `example.com`, even on URLs with many subdomains.


## cookieDomainPeriods, third-party cookies and legacy visitor identification

The implicit or explicit configuration of `cookieDomainPeriods` can have implications depending on whether third-party cookies are blocked and when you are using the legacy Adobe Analytics visitor identification service (setting the `s_vi` cookie). The following table illustrates four possible scenarios.

| Scenario | `cookieDomainPeriods` configuration is ... | Third-party cookies are blocked? | Result when using legacy Adobe Analytics visitor identification service |
|:---:|---|---|---|
| 1 | <span style="color:green">Correct</span> | No | Visitors are identified with an `s_vi` cookie set server-side. |
| 2 | <span style="color:green">Correct</span> | Yes | Visitors are identified with a fallback `s_fid` cookie set client-side (first-party page domain). |
| 3 | <span style="color:red">Incorrect</span> | No | Visitors are identified with fallback identifier based on combination of user agent and IP-address. The `s_vi` cookie is possibly set when `cookieDomainPeriods` is not transmitted properly.<br/>Link tracking and activity map cookies (`s_sq` cookie) cannot be set properly, so link interaction events will not be recorded. |
| 4 | <span style="color:red">Incorrect</span> | Yes | Visitors are identified with fallback identifier based on combination of user agent and IP-address. <br/>Link tracking and activity map cookies (`s_sq` cookie) cannot be set properly, so link interaction events will not be recorded.  |


>[!CAUTION]
>
>Be aware that you might have inadvertently configured `cookieDomainPeriods` <span style="color:red">incorrect</span>, when leaving it at its default value of `2` and using domains like `example.co.uk`. This implicit incorrect configuration results that you are identifying visitors following either scenario 3 or 4.
>
>AppMeasurement release 2.26.x or later configures `cookieDomainPeriods` automatically with the correct value. When updating to AppMeasurement release 2.26.x or later, only scenarios 1 or 2 are possible. When you plan to update to AppMeasurement release 2.26.x or later and you are currently identifiying visitors following scenario 3 or 4, this update has major implications:
>
>* Visitor identifiers are being reset and visitors will appear as new visitors. There will be no way to tie new activity to the previous visitor identifier.
>* Link tracking and activity map cookies will be restored, resulting in a sudden increase in link interactions appearing in reporting.
>
>While correctly configuring `cookieDomainPeriods` will improve AppMeasurement and Analytics functionality, it is recommended to assess whether you are affected by the changes resulting from upgrading your AppMeasurement library.
>
> See [Analytics Cookies](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=en) for more information about the cookies AppMeasurement uses.

## Domain periods using the Web SDK

The Web SDK can determine the correct cookie storage domain without this variable.

## Domain Periods using the Adobe Analytics extension

Domain Periods is a field under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
1. Expand the [!UICONTROL Cookies] accordion, which reveals the [!UICONTROL Domain Periods] field.

Set this field to `3` only on domains containing a period in its suffix. Otherwise this field can be left blank.

## s.cookieDomainPeriods in AppMeasurement and the Analytics extension custom code editor

The `cookieDomainPeriods` variable is a string that is typically set to `"3"`, only on domains that contain a period in its suffix. Its default value is `"2"`, which accommodates most domains.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
