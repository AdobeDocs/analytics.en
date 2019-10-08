---
title: useBeacon
description: useBeacon lets you force AppMeasurement to use the browsers sendBeacon API
keywords: Analytics Implementation
seo-description: useBeacon lets you force AppMeasurement to use the browsers sendBeacon API
---

# s.useBeacon

The `s.useBeacon` variable forces the next request to use the browser's [sendBeacon API](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon). Using `s.sendBeacon` allows an HTTP request to be sent outside of the context of a page. It is useful for exit links and other situations where you want to send off information before the page unloads.

Setting this value only applies to the next request that AppMeasurement fires. After the request fires, `s.useBeacon` resets to false. This variable applies to both `s.t()` and `s.tl()` image requests.

Using the `s.useBeacon` variable requires AppMeasurement 2.17.0 or higher.

> [!NOTE] [ExitLinks](s-linktrackvars.md) uses this variable automatically without any additonal configuration.

## Syntax

```js
s.useBeacon = true;
```
