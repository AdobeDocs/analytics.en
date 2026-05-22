---
title: Util.getQueryParam
description: Returns the value of a query string parameter.
feature: Appmeasurement Implementation
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/99nBiI23QwY6J6qEVKKz901Bertmkxf21YeJdKTmWbo'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
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
