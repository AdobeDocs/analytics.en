---
description: Scatter plots graph the elements of a data dimension (such as Page or City) on a grid in which the x- and y-axes represent different metrics.
seo-description: Scatter plots graph the elements of a data dimension (such as Page or City) on a grid in which the x- and y-axes represent different metrics.
seo-title: 2D scatter plots
solution: Analytics
title: 2D scatter plots
topic: Data workbench
uuid: ea1b0d4f-d1c7-44ca-bd4e-8cbacb5a38aa
index: y
internal: n
snippet: y
---

# 2D scatter plots

Scatter plots graph the elements of a data dimension (such as Page or City) on a grid in which the x- and y-axes represent different metrics.

Scatter plots can be useful when trying to understand the relationship between large numbers of disparate items, by two different metrics. In the following example, the scatter plot is showing each city by the number of visitors and the respective retention rate.

![](assets/vis_ScatterPlot_City.png)

The scatter plot enables you to quickly see the outliers. Salt Lake City, for example, has a higher than average retention rate per visitor.

Scatter plots can also be used to show the consistency of data. In the following example, the scatter plot shows the number of visitors with sessions of a particular length.

![](assets/vis_ScatterPlot_SessionDuration.png)

The size of each point on the scatter plot is determined by the radius metric. The default radius metric differs for each Adobe application. For example, in [!UICONTROL Site], the radius metric is based on Sessions by default. You can change the radius metric to have the points in your scatter plots represent any available metric. For steps to do so, see [Changing Radius Metrics](../../data-workbench-client/c-analysis-vis/c-scat-plots.md#section_FD80576D583C430CB469DAF12E39AA2A) The color of the points is based on the color legend that is open within the workspace. For more information about color legends, see [Color Legends](../../data-workbench-client/c-analysis-vis/c-legends/c-color-leg.md#concept_F84D51DC0D6547F981D0642FC2D01358).

## Select points {#section_4B4D45F39B884D54BB7407B3B2F4EA50}

**To select a single point **

* Click the point.

**To add another point or group of points to your selection**

* Ctrl+click a point or Ctrl+drag across multiple points.

**To remove a point or group of points from your selection**

* Shift+click a point or Shift+drag across several points.

## Changing dimensions {#section_796CD962EF3F476CAA89D99083782ED1}

* Right-click the label of the dimension at the top of the graph and click **[!UICONTROL Change Dimension]** > *< **[!UICONTROL dimension name]**>*.

## Changing metrics {#section_44B8BE9215CD4039B1EEB98AE1B31445}

**To change the metric shown on the x- or y-axis of a scatter plot**

* Right-click the label of the metric that you want to change and click **[!UICONTROL Change Metric]** > *< **[!UICONTROL metric name]**>*.

## Changing radius metrics {#section_FD80576D583C430CB469DAF12E39AA2A}

**To change the radius metric of a scatter plot**

Right-click the label of the dimension at the top of the graph and click **[!UICONTROL Change Radius Metric]** > *< **[!UICONTROL metric name]**>*.

![](assets/mnu_ScatterPlot_Change.png)

