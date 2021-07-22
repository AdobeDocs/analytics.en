---
title: Map data layer objects to data elements
description: Configure Launch to read from your data layer.
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
---
# Map data layer objects to data elements

Once your organization has established and implemented a data layer on your site, you can map data layer objects to data elements within Launch.

>[!NOTE]
>Adobe Experience Platform Launch has been rebranded as a suite of data collection technologies in Experience Platform. Several terminology changes have rolled out across the product documentation as a result. Please refer to the following [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) for a consolidated reference of the terminology changes.

## Prerequisites

[Create a data layer](../prepare/data-layer.md): Make sure a data layer exists on your site. While you technically can map any JavaScript object or scrape CSS elements directly from the page, Adobe recommends this practice as a last resort. If your site layout changes, the CSS selectors used in Launch stop working, causing data loss.

## Use Adobe Experience Platform Launch to create data elements

[Data elements](https://experienceleague.adobe.com/docs/launch/using/reference/manage-resources/data-elements.html#create-a-data-element) are components in Launch that you can use across the tool. You can assign variable values in the Adobe Analytics extension using data elements.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
1. Click the desired Launch property.
1. Click the **[!UICONTROL Data Elements]** tab, then click **[!UICONTROL Add Data Element]**.

    ![create data element](assets/createelement.png)

1. Enter a name for your data element. It can be a simple label that corresponds to a JavaScript variable in your data layer that you want to track.
1. Under the **[!UICONTROL Extension]** dropdown, select **[!UICONTROL Core]**.
1. Under the **[!UICONTROL Data Element Type]** dropdown, select **[!UICONTROL JavaScript Variable]**. A text field appears to the right that allows you to enter the JavaScript variable to map to this data element.
1. Enter the desired Javascript variable, typically within your data layer. For example, if your organization's data layer closely matches Adobe's recommended practice, a value could be `digitalData.page.pageInfo.pageName`. You can use your browser's console to validate JavaScript variable syntax and values.
1. Click **[!UICONTROL Save]**.

## Next steps

[Map data elements to Analytics variables](elements-to-variable.md): Assign data elements to Analytics variables so you can use them as dimensions in Analysis Workspace.
