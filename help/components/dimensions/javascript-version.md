---
title: JavaScript version
description: The JavaScript version supported by the visitor's browser.
feature: Dimensions
---
# JavaScript version

The 'JavaScript version' [dimension](overview.md) reports the JavaScript version supported by the visitor's browser. It does not report the version of the AppMeasurement library.

>[!IMPORTANT]
>
>This dimension is only available in Data Warehouse. If you want to use JavaScript version in other Analytics solutions, consider copying the value into an [eVar](evar.md) on every hit.

## Populate this dimension with data

AppMeasurement automatically detects JavaScript features in the browser and sends a version value in the `j` query string parameter. There is no implementation variable to set. This detection uses legacy JavaScript version labels; it is not a comprehensive measure of modern ECMAScript feature support.

| Property | Value |
| --- | --- |
| **AppMeasurement variable** | None (auto-collected) |
| **Web SDK / XDM field** | [`environment.browserDetails.javaScriptVersion`](/help/implement/aep-edge/xdm-var-mapping.md) |
| **Query parameter** | [`j`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML tag** | [`<javaScriptVersion>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Bulk Data Insertion API column** | [`javaScriptVersion`](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/column-reference) |
| **Byte limit** | 5 bytes |
| **Persistence** | Hit |

## Dimension items

Dimension items include the JavaScript version values collected from visitors' browsers, such as `1.5` and `1.6`.
