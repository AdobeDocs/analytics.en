---
title: Dimensions overview
description: Variables that contain string values.
feature: Dimensions
exl-id: dc00e06a-fdb5-40e3-82e2-269bad3b3677
---
# Dimensions overview

Dimensions are variables in Adobe Analytics that typically contain string values. Common dimensions include [Page](page.md), [Referring domain](referring-domain.md), or an [eVar](evar.md). In contrast, [metrics](../metrics/overview.md) contain numeric values that tie to a dimension. A basic report shows rows of string values (dimension), against a column of numeric values (metric).

For example, if you combined the 'Page' dimension with the 'Visits' metric, you would get a ranked report showing your top-visited pages:

| `Page` | `Visits` |
| --- | --- |
| `Home page` | `800` |
| `Product page` | `500` |
| `Purchase page` | `100` |

Each dimension represents a different part or facet of your site. You can combine one of more of these dimensions with one or more metric to create a desired report.

## Add dimension descriptions

Analytics administrators can add descriptions for dimensions and other components either within the Report Suite or directly within Analysis Workspace:

### Add descriptions to components in a Report Suite

Here is a video that describes how to add dimension (and metric) descriptions in Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/25453/?quality=12)

### Add descriptions to components in Analysis Workspace {#add-descriptions}

The Data Dictionary in Analysis Workspace helps both users and administrators keep track of and better understand the components in their Analytics environment. 

Part of this is the ability for Analytics administrators to add descriptions for components directly within Analysis Workspace. 

For more information about the Data Dictionary, see [Data Dictionary overview](/help/analyze/analysis-workspace/data-dictionary/data-dictionary-overview.md).

To add descriptions for components using the Data Dictionary:

1. Go to the Analysis Workspace project that contains the component for which you want to add a description.

1. Select the Data Dictionary icon on the left side of Analysis Workspace.

   The Data Dictionary window displays.

   ![data-dictionary.png](assets/data-dictionary.png)

1. Ensure the correct Report Suite is selected in the drop-down menu. 

1. In the search field, search for the component that you want to add the description to, then select it when it appears. 

1. Select the **Edit** icon, update the [!UICONTROL **Description**] field, then select [!UICONTROL **Save**]. <!-- Check this step -->
