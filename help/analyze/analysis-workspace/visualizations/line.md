---
description: Use the line visualization to depict trended (time-based) data sets
title: Line
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
feature: Visualizations
role: User, Admin
exl-id: d177b39f-add7-4011-977a-1bdf3a9368cb
---
# Line {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_line_button"
>title="Line"
>abstract="Create a line visualization that shows how values change over a period of time. A line visualization can only be used when time is used as a dimension."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_This article documents the Line visualization in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_See [Line](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/line)  for the_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** version of this article._

>[!ENDSHADEBOX]

The ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Line]** visualization represents metrics using a line to show how values change over a period of time. A line visualization can be used only when time is used as a dimension.

![Line visualization](assets/line-viz.png)


## Settings 

As part of the [visualization settings](freeform-analysis-visualizations.md#settings), specific line visualization settings are available.

| Setting | Description | 
|---|---|
| **[!UICONTROL Granularity]** | Select from the granularity drop-down to change a trended visualization from daily to weekly to monthly, etc. The granularity is also updated in the data source table. |
| **[!UICONTROL Show min]** <br/>**[!UICONTROL Show max]** | You can overlay a min and max value label to highlight the minimum and maximum values in a metric. The min/max values are derived from the visible data points in the visualization, not the full set of values within a dimension.<br/>![An overlay with the minimum and maximum value label.](assets/min-max-labels.png) |
| **[!UICONTROL Show trendline]** | You can choose to add a regression or moving average trendline to your line series. Trendlines help to depict a clearer pattern in the data. When selected, select a model from the list. See [Models](#models) for an overview and description of available models.<br/>![Linear trendline](assets/show-linear-trendline.png). | 

>[!TIP]
>
>It is recommended that trendlines be applied to data that does not include today (partial data) or future dates. Today or future dates skew the trendline. If you need to include future dates, however, remove zeroes from the data to prevent skewing for those days. Go to the visualization's data source table, choose your metric column, then enable **[!UICONTROL Column Settings]** > **[!UICONTROL Interpret zero as no value]**.



### Models

All regression model trendlines are fit using ordinary least squares:

| Model | Description |
| --- | --- |
| **[!UICONTROL Linear]** | Create a best-fit straight line for simple linear datasets and is useful when the data increases or decreases at a steady rate. Equation: `y = a + b * x` |
| **[!UICONTROL Logarithmic]** | Create a best-fit curved line and is useful when the rate of change in the data increases or decreases quickly and then levels out. A logarithmic trendline can use negative and positive values. Equation: `y = a + b * log(x)` |
| **[!UICONTROL Exponential]** | Create a curved line and is useful when data rises or falls at constantly increasing rates. This option should not be used if your data contains zero or negative values. Equation: `y = a + e^(b * x)` |
| **[!UICONTROL Power]** | Create a curved line and is useful for datasets that compare measurements that increase at a specific rate. This option should not be used if your data contains zero or negative values. Equation: `y = a * x^b` |
| **[!UICONTROL Quadratic]** | Finds the best-fit for a dataset shaped like a parabola (concave up or down). Equation: `y = a + b * x + c * x^2` |
| **[!UICONTROL Moving average]** | Create a smooth trendline based on a set of averages. Also known as a rolling average, a moving average uses a specific number of data points (determined by your [!UICONTROL Granularity] selection), averages them, and uses the average as a point in the line. Examples include a seven day moving average or a four week moving average.|

>[!MORELIKETHIS]
>
>[Add a visualization to a panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualization settings](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Visualization context menu](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

