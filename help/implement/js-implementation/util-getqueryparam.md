---
description: Returns the value of a specified query string parameter, if found in the current page URL or in the provided string.
keywords: Analytics Implementation
seo-description: Returns the value of a specified query string parameter, if found in the current page URL or in the provided string.
seo-title: Util.getQueryParam
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.getQueryParam
topic: Developer and implementation
uuid: 1fecd148-3e52-46f2-a73f-003563f7a62c
index: y
internal: n
snippet: y
---

# Util.getQueryParam

Returns the value of a specified query string parameter, if found in the current page URL or in the provided string.

 Because important data (such as campaign tracking codes, internal search keywords, etc.) is available in the query string on a page, getQueryParam helps capture the data into Analytics variables.

This utility replaces the [getQueryParam](../../implement/js-implementation/c-mplementation-plug-ins/getqueryparam.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) plug-in.

**Syntax:**

```
s.Util.getQueryParam(key, [url], [delim])
```

>[!NOTE]
>
>The syntax for the utility differs from the syntax for the plug-in.

**Parameters:** 

|  Parameter  | Description  |
|---|---|
|  key  | (required) The name of the query string parameter that you want to get. This parameter is case sensitive.  |
|  url  | (optional) Default url is `s.pageURL` or `window.location`. Specifying a value for this parameter overrides the URL from which the query parameter is retrieved to the one specified.  |
|  delim  | (optional) Parameter delimiter in the URL. Default delimiter is "&". This lets you to specify an alternate query-string delimiter, such as ";".  |

**Returns:**

This function returns the value of the query-string variable or an empty string if it's not found.

**Example:**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

