---
title: Map data layer objects to data elements
description: Configure tags to read from your data layer.
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/MmwNCdmt9TwNojJEyzbfTukeh4sKITk06gY-EBzjZPw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Map data layer objects to data elements

Once your organization has established and implemented a data layer on your site, you can map data layer objects to data elements within tags.

## Prerequisites

[Create a data layer](../prepare/data-layer.md): Make sure a data layer exists on your site. While you technically can map any JavaScript object or scrape CSS elements directly from the page, Adobe recommends this practice as a last resort. If your site layout changes, the CSS selectors used in tags stop working, causing data loss.

## Use tags to create data elements

[Data elements](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html) are components in Adobe Experience Platform Data Collection that you can use across the tool. You can assign variable values in the Adobe Analytics extension using data elements.

The following steps use the [Adobe Client Data Layer extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/client-data-layer/overview), which must be installed in your tag property.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Select the desired tag property.
1. Select the **[!UICONTROL Data Elements]** tab, then select **[!UICONTROL Add Data Element]**.

    ![create data element](assets/createelement.png)

1. Enter a name for your data element, such as `Page name`.
1. Under the **[!UICONTROL Extension]** drop-down list, select **[!UICONTROL Adobe Client Data Layer]**.
1. Under the **[!UICONTROL Data Element Type]** drop-down list, select **[!UICONTROL Data layer computed state]**.
1. Under **[!UICONTROL Return value]**, select **[!UICONTROL Specific path]**, then enter the path to the value in your data layer, such as `page.name`. To validate a path, run `adobeDataLayer.getState("page.name")` in your browser's console.
1. Select **[!UICONTROL Save]**.

Use these data elements in rules that the extension's **[!UICONTROL Data layer push]** event triggers, so that the data layer has loaded and contains the data from the push. See [Data element types](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/client-data-layer/data-element-types#computed-state).

### Object-based data layers {#object-based}

If your data layer is a JavaScript object, such as a CEDDL `digitalData` object, use the **[!UICONTROL JavaScript Variable]** data element type from the **[!UICONTROL Core]** extension instead. Enter the path to the value, such as `digitalData.page.pageInfo.pageName`. This data element type can't read the Adobe Client Data Layer, which stores its data in a computed state instead of in object properties.

## Next steps

[Map data elements to Analytics variables](elements-to-variable.md): Assign data elements to Analytics variables so you can use them as dimensions in Analysis Workspace.
