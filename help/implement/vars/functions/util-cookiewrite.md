---
title: Util.cookieWrite
description: Writes a value for a cookie.
---

# Util.cookieWrite

Cookies can store and retrieve information across pages on the same domain. Use the `Util.cookieWrite` method to set a value to a cookie. You can use the `Util.cookieRead` method to retrieve values set using `Util.cookieWrite`.

## Set cookies in Adobe Experience Platform Launch

Launch does not provide the ability to set cookies in the interface. Use the custom code editor, following AppMeasurement syntax.

## s.Util.cookieWrite() in AppMeasurement and Launch custom code editor

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
