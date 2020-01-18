---
title: pageURL
description: Override the automatically collected page URL on your site.
---

# pageURL

AppMeasurement automatically collects the page URL in each hit. If you want to override the page URL automatically collected by AppMeasurement, you can use this variable. You do not need to set this variable in most cases.

> [!NOTE] This variable is not an available dimension in Analysis Workspace. It is only available in Data Warehouse and Data Feeds. If you would like to use page URL as a dimension in Analysis Workspace, consider passing the `pageURL` variable into an eVar on every hit.

Sometimes URLs are longer than 255 bytes. AppMeasurement uses the `g` query string parameter for the first 255 bytes of the URL in image requests. If a URL is longer than 255 bytes, the rest of the URL is stored in the `-g` query string parameter. Protocol and query strings in the URL are included in this variable.

## Page URL in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.pageURL in AppMeasurement and Launch custom code editor

The `s.pageURL` variable is a string that contains the URL of the page. AppMeasurement automatically collects this variable, however you can override its value if desired.

```js
s.pageURL="https://example.com"
```

If you would like to use page URL as a dimension in reports, consider using the following in your implementation:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```
