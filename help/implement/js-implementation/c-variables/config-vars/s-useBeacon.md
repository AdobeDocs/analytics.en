---
description: useBeacon lets you force AppMeasurement to use the browsers sendBeacon API
keywords: Analytics Implementation
seo-description: useBeacon lets you force AppMeasurement to use the browsers sendBeacon API
solution: 
title: useBeacon
---

# s.useBeacon

The useBeacon property forces the next request to use the browser's [sendBeacon API](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon). The sendBeacon allows an HTTP request, like the Analytics tracking request, to be sent outside of the context of a page. This is useful for exit links and other situations where you want to send off information before the page unloads.  

Setting this value will only apply to the next request that AppMeasurement fires. After the request fire `s.useBeacon` will be reset to false. You can use this for any type of call regardless of whether it is `s.t()` or `s.tl()`.  

This is available in AppMeasurement version 2.17.0 and higher. 

>[!Note:] [ExitLinks](s-linktrackvars.md) will use this automatically without any additonal config.  

## Parameters

|Max Size|Debugger Parameter|Reports Populated|Default Value|
|--- |--- |--- |--- |
|N/A|N/A|N/A|false|

## Syntax and Possible Values

```js
s.useBeason = true
```
