---
title: Map data layer objects to data elements
description: Configure tags to read from your data layer.
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
TQID: https://experienceleague.adobe.com/MmwNCdmt9TwNojJEyzbfTukeh4sKITk06gY-EBzjZPw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
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

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Click the **[!UICONTROL Data Elements]** tab, then click **[!UICONTROL Add Data Element]**.

    ![create data element](assets/createelement.png)

1. Enter a name for your data element. It can be a simple label that corresponds to a JavaScript variable in your data layer that you want to track.
1. Under the **[!UICONTROL Extension]** drop-down list, select **[!UICONTROL Core]**.
1. Under the **[!UICONTROL Data Element Type]** drop-down list, select **[!UICONTROL JavaScript Variable]**. A text field appears to the right that allows you to enter the JavaScript variable to map to this data element.
1. Enter the desired Javascript variable, typically within your data layer. For example, if your organization's data layer closely matches Adobe's recommended practice, a value could be `digitalData.page.pageInfo.pageName`. You can use your browser's console to validate JavaScript variable syntax and values.
1. Click **[!UICONTROL Save]**.

## Next steps

[Map data elements to Analytics variables](elements-to-variable.md): Assign data elements to Analytics variables so you can use them as dimensions in Analysis Workspace.
