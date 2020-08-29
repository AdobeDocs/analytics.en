---
description: Use the line visualization to depict trended (time-based) data sets
title: Line
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
---

# Line

The Line visualization represents metrics using a line in order to show how values change over a period of time. A line chart can be used only when time is used as a dimension.

![Line visualization](assets/line-viz.png)

>[!IMPORTANT]
>
>Some Line visualization settings, such as [!UICONTROL Show trendline], are currently in limited testing. [Learn more](/help/landing/an-releases.md)

Click on the gear icon in the top right of the Line visualization to access [**Visualization settings**](freeform-analysis-visualizations.md) available. Settings are categorized into:

* **General**: Settings that are common across visualization types
* **Axis**: Settings that impact the x- or y-axis of the line visualization
* **Overlays**: Options for adding additional context to the series shown in your line visualization.

![Visualization settings](assets/viz-settings-modal.png)

## Change granularity

A granularity drop-down in the [visualization settings](freeform-analysis-visualizations.md) lets you change a trended visualization (e.g. line, bar) from daily to weekly to monthly, etc. The granularity is also updated in the data source table.

## Show min or max

Under **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show min/max]**, you can overlay a minimum and maximum value label to quickly highlight the peaks and valleys in a metric.

![Show min/max](assets/min-max-labels.png)

## Show trendline overlay

Under **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show trendline]**, you can choose to add a regression trendline to your line series. Trendlines help to depict a clearer pattern in the data.

![Linear trendline](assets/show-linear-trendline.png)

All models are fit using ordinary least squares:

|Model|Description|
|---|---|
|Linear|Creates a best-fit straight line for simple linear data sets and is useful when the data increases or decreases at a steady rate. Equation: `y = a + b * x`|
|Logarithmic|Creates a best-fit curved line and is useful when the rate of change in the data increases or decreases quickly and then levels out. A logarithmic trendline can use negative and positive values. Equation: `y = a + b * log(x)`|
|Exponential|Creates a curved line and is useful when data rises or falls at constantly increasing rates. This option should not be used if your data contains zero or negative values. Equation: `y = a + e^(b * x)`|
|Power|Creates a curved line and is useful for data sets that compare measurements that increase at a specific rate. This option should not be used if your data contains zero or negative values. Equation: `y = a * x^b`|
|Quadratic|Finds the best-fit for a data set shaped like a parabola (concave up or down). Equation: `y = a + b * x + c * x^2`|
