---
title: Metrics overview
description: View quantities of dimension items or data over time.
feature: Metrics
exl-id: 8dda3bc4-ffac-4407-896f-6064727d099c
---
# Metrics overview

Metrics allow you to quantify dimension items, such as to see which pages on your site have the most page views. You can also trend metrics over time, such as to see how many orders visitors make on your site each day. A basic report shows rows of string values (dimension), against a column of numeric values (metric).

For example, if you combined the 'Page' dimension with the 'Visits' metric, you would get a ranked report showing your top-visited pages:

| `Page` | `Visits` |
| --- | --- |
| `Home page` | `800` |
| `Product page` | `500` |
| `Purchase page` | `100` |

If you cannot find a given metric help page, it is likely either a [custom event](custom-events.md) or a [calculated metric](../c-calcmetrics/cm-overview.md).

* If the metric is a custom event, consult an Analytics admin within your organization, or the report suite's [solution design document](/help/implement/prepare/solution-design.md).
* If the metric is a calculated metric, click the information icon to determine its formula.

## Add metric descriptions

Analytics administrators can add descriptions for metrics and other components either within the Report Suite or directly within Analysis Workspace:

### Add descriptions to components in a Report Suite

Here is a video that describes how to add metric (and dimension) descriptions in Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/25453/?quality=12)

### Add descriptions to components in Analysis Workspace

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
