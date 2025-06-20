---
description: There are two ways to use metrics in Analysis Workspace.
title: Metrics in Analysis Workspace
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
---
# Metrics

Metrics allow you to quantify data points in Analysis Workspace. They are most commonly used as columns in a visualization and tied to dimensions.

## Types of metrics

Adobe offers several types of metrics for use in Analysis Workspace:

* **Standard metrics**: Most metrics that you use in projects are standard metrics. Examples include [Page views](/help/components/metrics/page-views.md), [Revenue](/help/components/metrics/revenue.md), or [Custom events](/help/components/metrics/custom-events.md). See [Metrics overview](/help/components/metrics/overview.md) in the Components user guide for more information.

* **Calculated metrics** ![Calculator](/help/assets/icons/Calculator.svg): User-defined metrics that are based on standard metrics, static numbers, or algorithmic functions. User-defined calculated metrics show a calculator icon in the list of available components. See [Calculated Metrics overview](/help/components/c-calcmetrics/cm-overview.md) in the Components user guide for more information.

* **Calculated metric templates** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg): Adobe-defined metrics that behave similarly to calculated metrics. You can use them as-is in Workspace projects, or save a copy to customize its logic. Calculated metric templates show an Adobe icon in the list of available components.

You can see whether a metric is approved ![Approved icon](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  or not. If you want more details on a metric, hover over the metric, and select ![Info icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). See [Component info](use-components-in-workspace.md#component-info) for more information.


## Use metrics in Analysis Workspace

Metrics can be used in various ways within Analysis Workspace. For information about how to add metrics and other types of components to Analysis Workspace, see [Use components in Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Use metrics](https://video.tv.adobe.com/v/40817?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Create calculated metrics

Calculated metrics allow you to easily see how metrics relate to each other, using simple operators or statistical functions. 


There are several ways to create calculated metrics. The method you choose determines whether the calculated metric is available from the component list across all projects, or only in the project where it was created.

### Create calculated metrics for all projects

You can use the [calculated metric builder](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-workflow.md) to [create calculated metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/). When created in this way, calculated metrics are available in the component list and can be used in projects throughout your organization. 


### Create calculated metrics for a single project

You can quickly create a calculated metric that is available only for the project where it was created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, right-click the column header of a single column.

   Or

   Select two columns while holding the Shift key, then right-click one of the selected columns.
   
1. Select **[!UICONTROL Create metric from selection]**

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the available options.

   When a single column is selected, the following options are available:

   * [!UICONTROL **Mean**]: Creates a new column that shows the mean value in the set of dimension elements for the column. This uses the [Mean](/help/components/c-calcmetrics/cm-reference/cm-functions.md#mean) function.
   
   * [!UICONTROL **Median**]: Creates a new column that shows the median value in the set of dimension elements for the column. This uses the [Median](/help/components/c-calcmetrics/cm-reference/cm-functions.md#median) function.

   * [!UICONTROL **Column max**]: Creates a new column that shows the largest value in the set of dimension elements for the column. This uses the [Column Maximum](/help/components/c-calcmetrics/cm-reference/cm-functions.md#column-maximum) function.

   * [!UICONTROL **Column min**]: Creates a new column that shows the smallest value in the set of dimension elements for the column. This uses the [Column Minimum](/help/components/c-calcmetrics/cm-reference/cm-functions.md#column-minimum) function.

   * [!UICONTROL **Column sum**]: Creates a new column that adds all numeric values for a metric within a column (across the elements of a dimension). This uses the [Column Sum](/help/components/c-calcmetrics/cm-reference/cm-functions.md#column-sum) function.

   When two columns are selected, the following options are available:

   * [!UICONTROL **Divide**]: Creates a new column that divides the values of the two selected columns.
   
   * [!UICONTROL **Subtract**]: Creates a new column that subtracts the values of the two selected columns.

   * [!UICONTROL **Add**]: Creates a new column that adds the values of the two selected columns.

   * [!UICONTROL **Multiply**]: Creates a new column that multiplies the values of the two selected columns.

   * [!UICONTROL **Percent change**]: Creates a new column that shows the percent change between the two selected columns.

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)


## Compare metrics with different attribution models

To quickly compare one attribution model to another, right click a metric and select **[!UICONTROL Compare Attribution Models]**:

![Compare attribution](assets/compare-attribution.png)

This shortcut lets you compare one attribution model to another without dragging in a metric and configuring it twice.

## Use the [!UICONTROL cumulative average] function to apply metric smoothing

Here is a video on the topic:


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cumulative average](https://video.tv.adobe.com/v/27068?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

