---
title: cookieDomain
description: The cookieDomain variable helps determine the domain to set cookies on.
---

# cookieDomain

The `cookieDomain` variable determines the domain where the cookies `s_cc` and `s_sq` are set. You can use this variable to explicitly set the cookie domain instead of using the `cookieDomainPeriods` variable.

This variable only needs to be used when both conditions are met:

* If your implementation uses first-party cookies. This variable is not required with implementations using `sc.omtrdc.net`.
* If your domain has a period in its suffix. For example, `example.co.uk` could use the `cookieDomain` variable to explicitly state that the cookie domain is `example.co.uk` and not `co.uk`.

## Cookie Domain in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## AppMeasurement syntax and Launch custom code

The `cookieDomain` variable is a string, and in most cases can simply be set to `window.location.hostname`.

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostname`. Instead of using `s.cookieDomainPeriods`, you can explicitly set `s.cookieDomain` to what you want to use in your implementation. For example, you could set cookies at the fully qualified page-name using:

`s.cookieDomain = window.location.hostname;` 
