---
title: writeSecureCookies
description: Allows AppMeasurement to set cookies with the Secure attribute.
---

# writeSecureCookies

The `writeSecureCookies` variable allows AppMeasurement to set [Secure cookies](https://en.wikipedia.org/wiki/Secure_cookie) for Analytics. This setting applies to both visitor ID cookies set by AppMeasurement, and cookies you set using the `Util.CookieWrite` method. It requires AppMeasurement 2.18.0 or higher.

> [!NOTE] If you enable the `writeSecureCookies` variable, make sure that all content on your site is served securely over HTTPS.

## Write Secure Cookies in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.writeSecureCookies in AppMeasurement and Launch custom code editor

The `s.writeSecureCookies` variable is a boolean that determines if AppMeasurement sets the Secure attribute when creating a cookie. Its default value is `false`. Set this variable to `true` if all content on your site is secure and you would like cookies set by AppMeasurement to have the Secure attribute.

```js
s.writeSecureCookies = true;
```
