---
title: cookieDomain
description: The cookieDomain variable helps determine the domain to set cookies on.
---

# cookieDomain

> [!IMPORTANT] This variable is retired. Use `trackingServer` instead.

The `cookieDomain` variable determines the domain where AppMeasurement sets cookies. You can use this variable to explicitly set the cookie domain instead of using the `cookieDomainPeriods` variable.

This variable only needs to be used when **both** of the following conditions are met:

* If your implementation uses first-party cookies. This variable is not required with implementations using a `trackingServer` value containing `sc.omtrdc.net`.
* If your domain has a period in its suffix. For example, `example.co.uk` could use the `cookieDomain` variable to explicitly state that the cookie domain is `example.co.uk` and not `co.uk`.

Only a small number of implementations have use for the `cookieDomain` variable, and even then, alternative variables like `cookieDomainPeriods` can be used instead.

## Cookie Domain in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.cookieDomain in AppMeasurement and Launch custom code editor

The `cookieDomain` variable is a string, and is set to the domain that you want to store cookies on.

```js
s.cookieDomain = "stats.example.com";
```
