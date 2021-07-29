---
title: useLinkTrackSessionStorage
description: Store link tracking data in session storage instead of a cookie.
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
---
# useLinkTrackSessionStorage

If your organization uses link tracking, AppMeasurement uses the `s_sq` cookie to pass information between hits. Some website configurations conflict with this cookie. If you would like to use browser session storage for link tracking and Activity Map data instead of a cookie, enable this variable.

Using a browser's session storage for link tracking comes with several limitations:

* Session storage does not work between protocols. For example, you have one page served over HTTP and the next page served over HTTPS. AppMeasurement cannot access link tracking data in session storage because of protocol differences.
* Session storage does not work across subdomains. For example, a visitor navigates to `store.example.com`, then navigates to `toys.example.com`. AppMeasurement cannot access link tracking data in session storage because of different subdomains.

>[!TIP]
>
>The most reliable implementation using session storage for link tracking serves all content through HTTPS on a single subdomain.

AppMeasurement removes session storage link tracking data after sending a hit to Adobe. It also automatically expires when the browser tab is closed.

## Use link track session storage using tags in Adobe Experience Platform

There is not a dedicated field in the Data Collection UI to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.useLinkTrackSessionStorage in AppMeasurement and custom code editor

The `s.useLinkTrackSessionStorage` variable is a boolean that determines if AppMeasurement uses session storage for link tracking data instead of the `s_sq` cookie. Its default value is `false`. Set this variable to `true` if you want AppMeasurement to use session storage instead of the `s_sq` cookie for link tracking and Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
