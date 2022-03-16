---
title: fpcookieDomainPeriods
description: Help AppMeasurement understand what domain to store cookies if your domain has a period in its suffix.
feature: Variables
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
---
# fpCookieDomainPeriods

The `fpCookieDomainPeriods` variable helps AppMeasurement determine where Analytics cookies are set by calling out that the domain suffix has an extra period in it. This variable allows AppMeasurement to accommodate the extra period in the domain suffix and set cookies in the right location. It inherits the value of [`cookieDomainPeriods`](cookiedomainperiods.md), but is still a best practice to set if you use a first-party cookie implementation.

* For domains like `example.com` or `www.example.com`, this variable does not need to be set. If needed, you can set this variable to `"2"`.
* For domains like `example.co.uk` or `www.example.co.jp`, set this variable to `"3"`.

>[!IMPORTANT]
>
>Do not take subdomains into account for this variable. For example, do not set `fpCookieDomainPeriods` on the example URL `store.toys.example.com`. AppMeasurement by default recognizes that cookies should be stored on `example.com`, even on URLs with many subdomains.

## First-party Domain Periods using tags in Adobe Experience Platform

First-party Domain Periods is a field under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Cookies] accordion, which reveals the [!UICONTROL First-party Domain Periods] field.

Set this field to `3` only on domains containing a period in its suffix. Otherwise this field can be left blank.

## s.fpCookieDomainPeriods in AppMeasurement and custom code editor

The `fpCookieDomainPeriods` variable is a string that is typically set to `"3"`, only on domains that contain a period in its suffix. Its default value is `"2"`, which accommodates most domains.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
