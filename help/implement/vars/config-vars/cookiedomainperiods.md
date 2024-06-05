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
* For domains like `example.co.uk` or `www.example.co.jp`, set this variable to `"3"`.


>[!IMPORTANT]
>
>Do not take subdomains into account for this variable. For example, do not set `cookieDomainPeriods` on the example URL `store.toys.example.com`. AppMeasurement by default recognizes that cookies should be stored on `example.com`, even on URLs with many subdomains.


## Cookie domain periods, third-party cookies and legacy visitor identification

Only when you are using the legacy Adobe Analytics visitor identification (instead of the recommended Experience Cloud Identity service), the implicit or explicit configuration of `cookieDomainPeriods` can have implications on how visitors are identified, depending on whether third-party cookies are blocked or not. 

The following table illustrates four possible scenarios.

| Scenario | `cookieDomainPeriods` configuration is ... | Third-party cookies are blocked? | Result when using legacy Adobe Analytics visitor identification service |
|:---:|---|---|---|
| 1 | <span style="color:green">Correct</span> | No | Visitors are identified with an `s_vi` cookie, set server-side. |
| 2 | <span style="color:green">Correct</span> | Yes | Visitors are identified with a fallback `s_fid` cookie, set client-side (first-party page domain). |
| 3 | <span style="color:red">Incorrect</span> | No | Visitors are identified with fallback identifier based on combination of user agent and IP-address. <br/>AppMeasurement is forced to set cookies as third-party cookies.<br/> The `s_vi` cookie is possibly set when `cookieDomainPeriods` is not transmitted properly. |
| 4 | <span style="color:red">Incorrect</span> | Yes | Visitors are identified with fallback identifier based on combination of user agent and IP-address.<br/>AppMeasurement is forced to set cookies as third-party cookies which are blocked, so no cookies are set. |

>[!CAUTION]
>
>You might have inadvertently configured `cookieDomainPeriods` <span style="color:red">incorrect</span> (leaving it at its default value of `"2"`) while using domains like `example.co.uk`. This implicit incorrect configuration results that you are identifying visitors following scenario 3 or 4.
>
>AppMeasurement release 2.26.x or later configures `cookieDomainPeriods` automatically with the correct value so only scenarios 1 or 2 are possible. When you update to AppMeasurement release 2.26.x or later, while currently identifiying visitors incorrectly (scenario 3 or 4), the update has major implications. 
>
>* Visitor identifiers are being reset and visitors will appear as new visitors. There will be no way to tie new activity to the previous visitor identifier. 
>* Cookies are set (such as for link tracking or activity map, e.g.`s_sq` cookie), resulting in sudden differences in reporting.
>
>While correctly configuring `cookieDomainPeriods` will improve AppMeasurement and Analytics functionality, it is recommended to assess whether you are affected by the changes resulting from upgrading your AppMeasurement library.
>
> See [Analytics Cookies](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html) for more information about the cookies AppMeasurement uses.

## Cookie domain periods using the Web SDK

The Web SDK can determine the correct cookie storage domain without this variable.

## Cookie domain periods using the Adobe Analytics extension

Domain Periods is a field under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
1. Expand the [!UICONTROL Cookies] accordion, which reveals the [!UICONTROL Domain Periods] field.

Set this field to `3` only on domains containing a period in its suffix. Otherwise this field can be left blank.

## Cookie domain periods in code AppMeasurement and the Analytics extension custom code editor

You can set the `cookieDomainPeriods` variable in the AppMeasurement Javascript library or in the custom code editor of the Analytics extension.

The `cookieDomainPeriods` variable is a string that is typically set to `"3"`, only on domains that contain a period in its suffix. Its default value is `"2"`, which accommodates most domains.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
