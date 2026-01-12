---
description: Use the key metric summary visualization to compare metric performance across two timelines.
title: Key Metric Summary
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
---
# Key metric summary {#key-metric-summary}

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Key metric summary"
>abstract="Create a visualization that is a combination of the line, summary change, and summary number charts. Use this visualization to compare how important metrics are trending between two periods of time."


>[!BEGINSHADEBOX]

_This article documents the Key metric summary visualization in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_See [Key metric summary](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/key-metric)  for the_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** version of this article._

>[!ENDSHADEBOX]


The ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key metric summary]** visualization lets you see how an important metric is trending within a single timeframe. It also lets you compare metric performance across two timeframes. It provides the benefits of multiple visualizations combined into one visualization:

* **[!UICONTROL Line]** visualization shows how the metric is trending for the primary and comparison date ranges

* **[!UICONTROL Summary percent change]** shows the metric increase or decrease between the primary and comparison date ranges

* Current total value ([!UICONTROL **summary number**]) for the metric

## Use cases

This visualization addresses various common use cases, including:

* An analyst trying to understand how opportunity creation looked this month compared to the same timeframe last year. 

* A marketer exploring how lead generation for a specific lead type has changed from this month to last month.

* An executive wanting to understand how new bookings changed from this quarter to last quarter.

## Use

1. Add a ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key metric summary]** visualization. See [Add a visualization to a panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Configure the visualization by selecting a **[!UICONTROL Metric]**, a **[!UICONTROL Primary date range]**, a **[!UICONTROL Comparison date range]** (optional) and a **[!UICONTROL Filter]** (optional):

   ![Key metric configuration showing the options for metric, primary date range, comparison date range, and segment.](assets/key-metrics-config.png)

   | Option| Description |
   | --- | --- |
   | **[!UICONTROL Metric]** | Select the metric you want to examine. All metrics are supported. |
   | **[!UICONTROL Primary date range]** | The current date range for the freeform table.<p>Choose from any available date ranges in your report suite.</p> <p>Choose [!UICONTROL **Panel date range**] if you want to use the same date range that is being used on the panel where the visualization is located.</p>  |
   | **[!UICONTROL Comparison date range]** | The date range that you want to compare with the primary date range. |
   | **[!UICONTROL Segment (optional)]** | Any segment that you are interested in for this summary.  |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >When the [!UICONTROL **Primary date range**] field is set to [!UICONTROL **Panel date range**], the **[!UICONTROL Comparison date range]** can automatically update, depending on whether the **[!UICONTROL Comparison date range]** option you choose is relative to the primary date range or fixed.
   >
   >* **Relative:** If the **[!UICONTROL Comparison date range]** field is set to an option that is relative to the primary date range (such [!UICONTROL **Previous day**], [!UICONTROL **Same day last week**], [!UICONTROL **Same day 4 weeks prior**], and so forth), then any updates to the [!UICONTROL **Primary date range**] field cause the **[!UICONTROL Comparison date range]** to automatically update to the period that immediately follows the date range of the panel.
   >* **Fixed:** If the [!UICONTROL **Comparison date range**] field is set to a fixed date range (such as **February 3, 2023**), then changes made to the [!UICONTROL **Primary date range**] field or the panel date range have no effect on the [!UICONTROL **Comparison date range**]. However, any updates to the panel date range cause the [!UICONTROL **Primary date range**] to automatically update.

1. Select **[!UICONTROL Build]**.

The output of the key metric summary looks like:

![Key metric output showing the metic, summary change, summary number, and line graphs.](assets/key-metrics.png)

Consider the following when viewing the output:

* The **[!UICONTROL Previous period]** line graph (always displayed in gray) corresponds to the **[!UICONTROL Comparison date range]** in the configuration step.

* If a comparison date range is not specified during configuration or is hidden in the visualization settings, only the line graph for the primary date range is displayed. The summary change is hidden. 

* From here, you can hover over the line graphs to see the statistics for individual days:


## Configure

After building the visualization, you can edit the original configuration. 

1. Select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Configure visualization]** at the top of the visualization.

   You are taken back to the original configuration dialog. 

1. Change the settings as preferred. Select **[!UICONTROL Reset]** to reset the current settings. Select **[!UICONTROL Build]** to rebuild the visualization.

## Settings

As part of the visualization settings, specific key metric summary settings are available.

| Setting | Description |
| --- | --- |
| **[!UICONTROL Emphasize percent change]** | Display summary change in prominent bold type in the center of the visualization |
| **[!UICONTROL Emphasize number value]** | Display summary number in prominent bold type in the center of the visualization |
| **[!UICONTROL Legend visible]** | Show or hide the legend at the bottom of the visualization |
| **[!UICONTROL Show annotations]** | Show or hide annotations added by an admin |
| **[!UICONTROL Hide title]** | Hide the visualization's title. |
| **[!UICONTROL Percentages]** | Displays the visualization in a percentage instead of a number. |
| **[!UICONTROL Show trendlines]** | Show trendlines in the visualization. |
| **[!UICONTROL Show max and min on trendlines]** | Show or hide minimum and maximum values on primary and comparison line charts |
| **[!UICONTROL Show comparison percentage and trendline]** | Show or hide comparison data. When hidden, both the comparison line chart and summary change objects are hidden from view. |
| **[!UICONTROL Show total number]** | Show or hide summary number |
| **[!UICONTROL Show raw difference]** | Show or hide raw difference between the total value of the metric in the primary date range and the secondary date range |
| **[!UICONTROL Abbreviate value]** | Select **[!UICONTROL Abbreviate value]** to abbreviate intelligently the number value. When selected, enter a number to define the amount of abbreviation. For example:<br/><table><tr><td>**Original value**</td><td>**Abbreviation**</td><td>**Result**</td></tr><tr><td>$12,011,141.25</td><td>Not selected</td><td align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>Selected, set to 1</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td>Selected, set to 2</td><td align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>Selected, set to 2</td><td align="right">$12.011M</td></tr><tr><td>$12,011,141.25</td><td>Select, set to 3</td><td align="right">$12.011M</td></tr></table> |

## Edit visualization

After you build the visualization, you can edit the original configuration. 

1. Select ![Edit](/help/assets/icons/Edit.svg) in the top-right corner of the visualization.


   You are now taken back to the original [configuration view](#configure). 

1. Change the metric, primary date range, comparison date range, or segment as preferred.

>[!MORELIKETHIS]
>
>[Add a visualization to a panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualization settings](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Visualization context menu](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)

