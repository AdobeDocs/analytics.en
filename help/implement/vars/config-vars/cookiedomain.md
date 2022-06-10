---
title: cookieDomain
description: The cookieDomain variable helps determine the domain to set cookies on.
feature: Variables
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
---
# cookieDomain

>[!IMPORTANT]
>
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
