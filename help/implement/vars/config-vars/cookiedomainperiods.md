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

>[!CAUTION]
>
>If you have incorrectly configured `cookieDomainPeriods` (or are using the default of `2` while using a domain like `example.co.uk`) this has implications on:
>
> * **Visitor identification** (`s_vi` and `s_fid` cookies) when using the legacy Adobe Analytics visitor identification. AppMeasurement will not be able to set or read the `s_vi` cookie. If third-party cookies are supported, AppMeasurement will set the `s_fid` cookie instead. If third-party cookies are not supported, AppMeasurement will not be able to set the `s_fid` cookie, and an identifier is generated server side.<br/>Visitor identification is not impacted when using the Experience Cloud Identity service.
> * **Link Tracking and Activity Map** (`s_sq` cookie): These cookies are used to temporarily store link interaction information, so this information can be included on subsequent AppMeasurement calls. When these cookies cannot be set properly these events will not be recorded. 
>
> With the latest AppMeasurement release () configures `cookieDomainPeriods` automatically with the correct value and, as a result, cookies are properly set. When you have incorrectly configured `cookieDomainPeriods` (or are using the default of `2` while using a domain like `example.co.uk`) before the update, and plan to update to the latest AppMeasurement, that update will have significant impact on reporting:
>
> * **Visitor identification**: AppMeasurement will be able to set an identifier using the `s_vi` cookie which will take precedence over the `s_fid` identifier or server-side identifier used before the update. This results in the visitor identifier being reset. The visitor will appear as a new visitor and there will be no way to tie new activity to the previous identifier. 
> * **Link Tracking and Activity Map**: Link tracking will be restored, resulting in a sudden increase in link interactions appearing in reporting.
>
> While correctly configuring `cookieDomainPeriods` will improve AppMeasurement and Analytics functionality, it is recommended to assess whether you are affected by the changes resulting from upgrading your AppMeasurement library.
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
