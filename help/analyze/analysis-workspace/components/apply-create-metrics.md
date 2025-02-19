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

  ![Standard metric](assets/standard-metric.png)

* **Calculated metrics**: User-defined metrics that are based on standard metrics, static numbers, or algorithmic functions. User-defined calculated metrics show a calculator icon in the list of available components. See [Calculated Metrics overview](/help/components/c-calcmetrics/cm-overview.md) in the Components user guide for more information.

  ![Calculated metric](assets/calculated-metric.png)

* **Calculated metric templates**: Adobe-defined metrics that behave similarly to calculated metrics. You can use them as-is in Workspace projects, or save a copy to customize its logic. Calculated metric templates show an Adobe icon in the list of available components.

  ![Calculated metric template](assets/calculated-metric-template.png)

## Use metrics in Analysis Workspace

Metrics can be used in various ways within Analysis Workspace. For information about how to add metrics and other types of components to Analysis Workspace, see [Use components in Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Use metrics](https://video.tv.adobe.com/v/40817?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



## Create calculated metrics

Calculated metrics allow you to easily see how metrics relate to each other using simple operators or statistical functions. 

There are several ways to create calculated metrics. The method you choose determines whether the calculated metric is available from the component list across all projects, or only in the project where it was created.

### Create calculated metrics for all projects

You can use the calculated metric builder to create calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. 

For information about how to access the calculated metrics builder, see [Build metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

### Create calculated metrics for a single project

You can create quick calculated metrics that are available only for the project where they were created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, right-click one or more header column cells, then select **[!UICONTROL Create metric from selection]**

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the following options:

   * [!UICONTROL **Divide**]
   
   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Add**]

   * [!UICONTROL **Multiply**]

   Or, to open the calculated metric builder and create the calculated metric for all projects, select [!UICONTROL **Open in Calculated Metric Builder**], then continue with [Build metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)

## Compare metrics with different attribution models

If you'd like to quickly and easily compare one attribution model to another, right click a metric and select **[!UICONTROL Compare Attribution Models]**:

![Compare attribution](assets/compare-attribution.png)

This shortcut lets you quickly and easily compare one attribution model to another without dragging in a metric and configuring it twice.

## Use the [!UICONTROL cumulative average] function to apply metric smoothing

Here is a video on the topic:


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cumulative average](https://video.tv.adobe.com/v/27068?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

