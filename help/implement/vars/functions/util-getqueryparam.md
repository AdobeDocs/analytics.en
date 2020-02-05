---
title: Util.getQueryParam
description: Returns the value of a query string parameter.
---

# Util.getQueryParam

Query string parameters in a browser URL frequently contain important data for Analytics. Use the `Util.getQueryParam` method to retrieve data from the query string.

## Get query string parameter data in Adobe Experience Platform Launch

You can get query string parameter data by setting values in data elements.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Data Elements] tab, then click the desired data element (or create a data element).
4. Set the [!UICONTROL Extension] dropdown to [!UICONTROL Core], and the [!UICONTROL Data Element Type] to [!UICONTROL Query String Parameter].
5. Enter the query string parameter in the text field.

The query string parameter value is stored in the data element. You can then reference the data element in rules to assign Analytics variables.

## s.Util.getQueryParam() in AppMeasurement and Launch custom code editor

Call the `s.Util.getQueryParam()` method to retrieve a query string value from the browser URL. The string argument containing a query string parameter is required. This method returns a string, which you can assign to Analytics variables:

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

A second optional argument allows you to specify the string to check for query string parameters. By default, the utility looks at the browser URL.

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

A third optional argument allows you to customize the query string delimiter. Its default value is `&`. You can change this value if your query string uses a different delimiter.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

> [!NOTE] Previous versions of AppMeasurement had a plug-in named `s.getQueryParam` available. This plug-in is no longer needed, as it is now included in AppMeasurement by default.
