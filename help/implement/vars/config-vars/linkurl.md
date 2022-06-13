---
title: linkURL
description: Override the automatically generated link URL AppMeasurement uses in link tracking calls.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
---
# linkURL

Whenever a link tracking call is sent to Adobe, data collection servers automatically detect the URL. Use the `linkURL` variable to override the detected URL.

## Link URL using the Web SDK

Link URL is [mapped for Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under the XDM field `web.webInteraction.URL`.

## Link URL using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.linkURL in AppMeasurement and the Analytics extension custom code editor

The `s.linkURL` variable is a string, containing the URL of the browser when the link was clicked. This variable does not populate any dimensions available in reporting.

```js
s.linkURL = "https://example.com";
```

If the third argument of the [tl()](../functions/tl-method.md) method is not set, the `linkURL` variable is used instead.
