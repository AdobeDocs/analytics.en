---
title: Segment comparison panel overview
description: Learn how to use the segment comparison panel, part of Segment IQ in Analysis Workspace.
keywords: Analysis Workspace;Segment IQ
feature: Segmentation
role: User, Admin
exl-id: 1f5df6fb-1e9f-4b8f-885c-bf9e68d88c89
---
# Segment comparison panel overview {#segment-comparison-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_button"
>title="Segment comparison"
>abstract="Quickly compare two segments across all data points to automatically find relevant differences."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_panel"
>title="Segment comparison panel"
>abstract="Quickly compare two segments across all data points to automatically find relevant differences.<br/><br/>**Parameters**<br/>**Add a segment**: The first segment you want to analyze.<br/>**Compare against**: The second segment you want to compare against. This will automatically populate with *Everyone Else* which is the inverse of your first segment. You can replace this with a different segment if desired.<br/>**Advanced settings**: The ability to exclude components from being analyzed in the segment comparison."
<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_This article documents the Segment comparison panel in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_There is no equivalent panel in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]

The Segment comparison panel is a tool part of [Segment IQ](../../segment-iq.md) that discovers the most statistically significant differences among an unlimited number of segments. The feature iterates through an automated analysis of all dimensions and metrics that you have access to. It automatically uncovers key characteristics of the audience segments that are driving your company's KPIs and lets you see how much any segments overlap.

+++ Here is a video on segment comparison:

>[!VIDEO](https://video.tv.adobe.com/v/23976/?quality=12)

+++

## Use

To use an **[!UICONTROL Attribution]** panel:

1. Create an **[!UICONTROL Attribution]** panel. For information about how to create a panel, see [Create a panel](../panels.md#create-a-panel).

1. Specify the [input](#panel-input) for the panel.

1. Observe the [output](#panel-output) for the panel.



### Panel input

You can configure the [!UICONTROL Segment comparison] panel using these input settings:

![Segment comparison input panel](assets/segment-comparison-input.png)

| Input | Description |
| --- | --- |
| **[!UICONTROL Add a segment]** | Select the dimension you want to compare against. |
| **[!UICONTROL Compare against]** | Select the dimension you want to use to compare the inital selected segment. If you do not select a specific segment, the default segment **[!UICONTROL Everyone else]** is used. |
| **[!UICONTROL Show / hide advanced settings]** | Select **[!UICONTROL Show advanced settings]** to configure **[!UICONTROL Excluded components]**, select **[!UICONTROL Hide advanced settings]** to hide **[!UICONTROL Excluded components]**. |
| **[!UICONTROL Excluded components]** | Components you can specify, like **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]** or **[!UICONTROL Segments]** for exclusion.<br><ul><li>Drag and drop one or more dimensions, metrics or segments from the containers into the **[!UICONTROL Excluded components]** container.</li><li>To remove a component, select the type (**[!UICONTROL Dimension]** **[!UICONTROL Metrics]**, or **[!UICONTROL Segments]**) and select ![CrossSize75](/help/assets/icons/CrossSize75.svg) to remove a component. To remove all components, select **[!UICONTROL Clear all]**.</li><li>To set the current selection of dimensions, metrics and segments as the default, select **[!UICONTROL Set as default]**.</li></ul> |

Select **[!UICONTROL Build]** to build the panel.

### Panel output

Once Adobe Analytics finishes analyzing the two desired segments, the output panesl shows results through several visualizations:

![Panel output segment comparison](assets/segment-comparison-output.png)

| Visualization | Description |
|---|---|
| **[!UICONTROL Size and overlap]** | Illustrates with a [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) visualization the comparative sizes of each selected segment and how much they overlap with each other. |
| **[!UICONTROL Unique visitors for 1st segment]** | A [Summary number](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) visualization showing the unique visitors for the first segement (in the example Single Page Visits) |
| **[!UICONTROL Unique visitors for 2nd segment]** | A [Summary number](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) visualization showing the unique visitors for the second segement (in the example First Time Visits) |
| **[!UICONTROL Top metrics agains Segments]** | A [Freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) showing top metrics for the selected segments. |
| **[!UICONTROL Metric over time by Segment]** | A [Line](/help/analyze/analysis-workspace/visualizations/line.md) visualization showing the metrics over time for the selected segments. |
| **[!UICONTROL Top dimension items against Segments]** | A [Freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) showing the mixed dimension items for the selected segments. |
| **[!UICONTROL Dimension items by Segments]** | A [Horizontal bar](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) visualization showing the dimension items by segment. |
| **[!UICONTROL Top segments against Segments]** | A [Freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) that shows the top segments against Segments. |
| **[!UICONTROL Segment overlap]** | A [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) visualization that shows the segment overlap. |

Use ![Edit](/help/assets/icons/Edit.svg) to reconfigure and rebuild the panel.


<!--
#### Size and overlap

Illustrates the comparative sizes of each selected segment and how much they overlap with each other using a venn diagram. You can hover over the visual to see how many visitors were in each overlapping or non-overlapping section. You can also right click on the overlap to create a brand new segment for further analysis. If the two segments are mutually exclusive, no overlap is shown between the two circles (typically seen with segments using a hit container).

![Size and overlap](assets/size-overlap.png)

#### Population summaries

To the right of the Size and Overlap visualization, the total unique visitor count in each segment and overlap is shown.

![Population summaries](assets/population_summaries.png)

#### Top metrics

Displays the most statistically significant metrics between the two segments. Each row in this table represents a differentiating metric, ranked by how different it is between each segment. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific metric is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific metric. If a metric is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Metrics added to this table after the segment comparison has finished do not receive a Difference Score.

![Top metrics](assets/top-metrics.png)

#### Metric over time by segment

To the right of the metrics table is a linked visualization. You can click a line item in the table on the left, and this visualization updates to show that metric trended over time.

![Top metrics line](assets/linked-viz.png)

#### Top dimensions

Shows the most statistically significant dimension items across all of your dimensions. Each row shows the percentage of each segment exhibiting this dimension item. For example, this table might reveal that 100% of visitors in 'Segment A' had the dimension item 'Browser Type: Google', whereas only 19.6% of 'Segment B' had this dimension item. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific dimension item is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific dimension item. If a dimension item is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Dimension items added to this table after the segment comparison has finished do not receive a Difference Score.

![Top dimensions](assets/top-dimension-item1.png)

#### Dimension items by segment

To the right of the dimensions table is a linked bar chart visualization. It shows all displayed dimension items in a bar chart. Clicking a line item in the table on the left updates the visualization on the right.

![Top dimensions bar chart](assets/top-dimension-item.png)

#### Top segments

Shows which other segments (other than the two segments selected for comparison) have statistically significant overlap. For example, this table can show that a third segment, 'Repeat Visitors', overlaps highly with 'Segment A' but does not overlap with 'Segment B'. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific segment is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific segment. If a segment is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Segments added to this table after the segment comparison has finished do not receive a Difference Score.

![Top segments](assets/top-segments.png)

#### Segment overlap

To the right of the segments table is a linked venn diagram visualization. It shows the most statistically significant segment applied to your compared segments. For example, 'Segment A' + 'Statistically significant segment' vs. 'Segment B' + 'Statistically significant segment'. Clicking a segment line item in the table on the left updates the venn diagram on the right.

![Top segments venn diagram](assets/segment-overlap.png)

-->
