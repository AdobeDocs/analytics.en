---
title: Util.getQueryParam
description: Returns the value of a query string parameter.
feature: Variables
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
---
# Util.getQueryParam

Query string parameters in a browser URL frequently contain important data for Analytics. Use the `Util.getQueryParam()` method to retrieve data from the query string.

## Get query string parameter data using the Adobe Analytics extension and Web SDK extension

You can get query string parameter data by setting values in data elements.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Data Elements] tab, then click the desired data element (or create a data element).
4. Set the [!UICONTROL Extension] drop-down list to **[!UICONTROL Core]**, and the [!UICONTROL Data Element Type] to **[!UICONTROL Query String Parameter]**.
5. Enter the query string parameter in the text field.

The query string parameter value is stored in the data element. You can then reference the data element in rules to assign the desired variables.

## s.Util.getQueryParam() in AppMeasurement and the Analytics extension custom code editor

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

>[!TIP]
>
>A similar plug-in named [`s.getQueryParam`](../plugins/getqueryparam.md) is available. This plug-in contains more advanced features, but is also more complex and not included in AppMeasurement by default.
