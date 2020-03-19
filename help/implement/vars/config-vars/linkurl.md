---
title: linkURL
description: Override the automatically generated link URL AppMeasurement uses in link tracking calls.
---

# linkURL

Whenever a link tracking call is sent to Adobe, data collection servers automatically detect the URL. Use the `linkURL` variable to override the detected URL.

## Link URL in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.linkURL in AppMeasurement and Launch custom code editor

The `s.linkURL` variable is a string, containing the URL of the browser when the link was clicked. This variable does not populate any dimensions available in reporting.

```js
s.linkURL = "https://example.com";
```

If the [`linkName`](linkname.md) variable is not set for a link tracking call, the `linkURL` variable is used instead.
