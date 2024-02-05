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

>[!WARNING]
>
>With the latest [AppMeasurement release](../../appmeasurement-updates.md), `cookieDomainPeriods` will be configured automatically. This has major visitor identification implications for you, when you:
>
> * are using AppMeasurement in your implementation of Adobe Analytics, instead of the (recommended) Adobe Experience Platform Web SDK,
> * are using domains like `example.co.uk`,
> * using the [`visitorID`](visitorid.md) configuration variable (Visitor ID service) instead of the (recommended) Experience Cloud ID service,
> * have not explictly set `cookieDomainPeriods` in your configuration (so it is implicitly incorrectly set to its default `2`),
> * are using a fallback id ([`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html_) cookie) to track visitors who are using browsers that block third-party cookies.
>
> If you deploy the latest AppMeasurement library without taking precautions, the following happens automatically:
>
> 1. The `cookieDomainPeriods` is automatically set to `3` based on the new AppMeasurement functionality.
> 2. AppMeasurement will start setting the [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html) cookie, which will replace the fallback id you have been using to collect visitor information despite the blocking of third part cookies.
> 
> As a result, the visitor identification data you collect is going to be dramatically impacted.
>


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
