---
title: useBeacon
description: useBeacon lets you force AppMeasurement to use the browsers sendBeacon API
---

# useBeacon

Most modern browsers include the native method `navigator.sendBeacon()`. It asynchronously sends a small amount of data over HTTP to a web server. AppMeasurement can use the `navigator.sendBeacon()` method if the `useBeacon` variable is enabled. It is useful for exit links and other situations where you want to send information before the page unloads.

If `useBeacon` is enabled, the next hit sent to Adobe uses the browser's `navigator.sendBeacon()` method instead of a standard `GET` image request. This variable applies to both `s.t()` and `s.tl()` image requests. It requires AppMeasurement 2.17.0 or higher.

> [!TIP] AppMeasurement automatically enables `useBeacon` for exit link image requests.

The `useBeacon` variable is ignored when the visitor uses a browser that does not support `navigator.sendBeacon()`. Use of this variable requires AppMeasurement 2.16.0 or higher.

## Use Beacon in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.useBeacon in AppMeasurement and Launch custom code editor

The `s.useBeacon` variable is a boolean that determines if AppMeasurement uses the browser's `navigator.sendBeacon()` method. Its default value is `false`. Set this variable to `true` before calling a tracking function if you want to use the asynchronous nature of `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

> [!NOTE] After a tracking call runs, this variable is reset to `false`. If your implementation sends multiple image requests in the same page load (such as single-page applications), set this variable to `true` before each tracking call.
