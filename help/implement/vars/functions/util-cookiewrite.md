---
title: Util.cookieWrite
description: Writes a value for a cookie.
feature: Variables
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
---
# Util.cookieWrite

Cookies can store and retrieve information across pages on the same domain. Use the `Util.cookieWrite()` method to set a value to a cookie. You can use the [`Util.cookieRead()`](util-cookieread.md) method to retrieve values set using `Util.cookieWrite()`.

## Set cookies using the Adobe Analytics extension and the Web SDK extension

Adobe Experience Platform Data Collection does not provide the ability to set cookies in the interface.

## s.Util.cookieWrite() in AppMeasurement and the Analytics extension custom code editor

Call the `s.Util.cookieWrite()` method to set a cookie to a desired value.

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

An optional third argument is available that determines when the cookie expires. Cookies set using `s.Util.cookieWrite()` expire at the end of the browser session by default.

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## Examples

You can instantiate a variable upon success of writing a cookie. This variable is a boolean.

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
