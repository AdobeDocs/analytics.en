---
title: Util.cookieWrite
description: Writes a value for a cookie.
feature: Appmeasurement Implementation
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/VxNoO8-K6rE8NdIgQSA0ubuBwaHXu2OPLCexzNCXdHQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
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
