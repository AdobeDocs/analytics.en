---
description: Lean how to configure and specify the touchpoints to create a multi-dimensional fallout sequence.
title: Configure A Fallout Visualization
feature: Visualizations
role: User, Admin
exl-id: 9d2a0163-a5cb-4a1c-97e9-e78a8f99aaee
---
# Configure a fallout visualization

You can specify the touchpoints to create a multi-dimensional fallout sequence. Commonly, a touchpoint is a page on your site. However, touchpoints are not limited to pages. For example, you can add events, such as units, as well as unique persons and return visits. You can also add dimensions, such as a category, browser type, or internal search term.

You can even add segments within a touchpoint. For example, you might want to compare segments, such as iOS and Android&trade; users. Drag the desired segments to the top of the fallout and information about those segments is added to the fallout report. If you want to show only those segments, you can remove the All Visits baseline.

There is no limitation on the number of steps that you can add or the number of dimensions used.

You can do pathing on dimensions, metrics, and segments. For example, suppose that someone is looking at shoes, shirt on one page, and on the next page they're looking at shirt, socks. The next product flow report from shoes will be shirt and socks, NOT shirt.

## Use

1. Add a ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Fallout]** visualization. See [Add a visualization to a panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Drag a component to the **[!UICONTROL Add touchpoint]** drop-down menu.

   For example, you can add a single page to the fallout report, rather than the entire dimension. Click the right arrow ![ChevronRight](/help/assets/icons/ChevronRight.svg) on the page dimension to pick a specific page, such as **[!UICONTROL home]**, to add to the Fallout report.

   ![The home page from the Home page dimension dragged to the Add Touchpoint field.](assets/fallout-drag.png)

1. Continue adding touchpoints until your sequence is complete.

   The circled numbers in the gray portion of the bar show the fallout between touchpoints (not the overall fallout to that point). The **[!UICONTROL Touchpoint %]** shows the successful fall through from the previous step to the current step in the fallout report.

   ![The Page:CamerRoll or Page: Camera touchpoints highlighted.](assets/fallout-or.png)

   When adding touchpoints, you can do any of the following:

   * Combine multiple components by dragging one or more additional components onto a single touchpoint.

     >[!NOTE]
     >
     >Multiple segments are joined with AND, but multiple items such as dimension items and metrics are joined with OR.

   * Reorder touchpoints by dragging them to a different level within the fallout hierarchy.
   
   * Combine a touchpoint with another touchpoint. To combine touchpoints, drag one touchpoint onto another. Drop it when you see the word **[!UICONTROL Combine]**.

     ![Combine touchpoints](assets/fallout-combine-touchpoints.png)

   * Constrain individual touchpoints to the next event (as opposed to *eventually*) within the path. Beneath each touchpoint, there is a selector with the options **[!UICONTROL Eventual path]** and **[!UICONTROL Next event]**, as shown here:

     ![The All Visits view showing the Eventual Path option highlighted. ](assets/fallout-nexthit.png)

     | Option | Description |
     |---|---|
     | **[!UICONTROL Eventual path]** (default) | Visitors are counted that will *eventually* land on the next page in the path, but not necessarily on the next event. |
     | **[!UICONTROL Next event]** | Visitors are counted that will land on the next page in the path on the very next event. |

   * Hover over a touchpoint to see the fallout and other information about that level. Information includes the touchpoint's name, the person count, and success rate. You can also compare the success rate to other touchpoints.
    
     ![Touchpoint tooltip](assets/fallout-tooltip.png)


## Settings

As part of the visualization, specific settings are available.

| Fallout container | Description |
|--- |--- |
| **[!UICONTROL Session]** or **[!UICONTROL Person]**|  Switch between [!UICONTROL Session] and [!UICONTROL Person] to analyze person pathing. The default is [!UICONTROL Person]. These settings help you understand person engagement at the person level (across sessions), or constrain the analysis to a single session. |


## Context menu

As part of the visualization, specific context menu options are available. 

### Access the context menu

You can access the context menu in either of the following ways:

* Hover over a touchpoint in the visualization, then select **[!UICONTROL Click to analyze]**. 

  ![Access context menu from hover](assets/fallout-tooltip-analyze.png)

* Right-click a touchpoint in the visualization.

  ![Fallout options](assets/fallout-options.png)

### Context menu options

The following context menu options are available:

| Option | Description |
|--- |--- |
|**[!UICONTROL Trend touchpoint]**|See trend data for a touchpoint in a line graph, with some pre-built anomaly detection data.|
|**[!UICONTROL Trend touchpoint (%)]**|Trends the total fallout percentage.|
|**[!UICONTROL Trend all touchpoints (%)]**|Trends all the touchpoint percentages in the fallout (except **[!UICONTROL All People]**, if it's included), on the same chart.|
|**[!UICONTROL Breakdown fallthrough at this touchpoint]**|View what visitors did between two touchpoints (this touchpoint and the next touchpoint) if they continued to the next touchpoint. This option creates a freeform table showing your dimensions. You can replace dimensions and other elements of the table. For example, a table that is labeled **[!UICONTROL Fallthrough: All Visitors > Page equals any of home]** and contains **[!UICONTROL Page]** as the dimension and **[!UICONTROL Unique Visitors]** segmented by the [project-only quick segment](/help/components/segmentation/segmentation-workflow/seg-quick.md) **[!UICONTROL Fallthrough: All Visitors > Page equals any of home]** as the metric. Inspect the segment to understand how the fallthrough segment is determined. |
|**[!UICONTROL Breakdown fallout at this touchpoint]**| View what visitors who did not make it through the funnel did immediately after the selected step. This option creates a freeform table showing your dimensions. You can replace dimensions and other elements of the table. For example, a table that is labeled **[!UICONTROL Fallout: All Visitors > Page equals any of home]** and contains **[!UICONTROL Page]** as the dimension and **[!UICONTROL Unique Visitors]** segmented by the [project-only quick segment](/help/components/segmentation/segmentation-workflow/seg-quick.md) **[!UICONTROL Fallthrough: All Visitors > Page equals any of home]** segment as the metric. Inspect the segment to understand how the fallout segment is determined. |
|**[!UICONTROL Create segment from touchpoint]**|Create a new segment from the selected touchpoint.|

>[!MORELIKETHIS]
>
>[Add a visualization to a panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualization settings](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Visualization context menu](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

