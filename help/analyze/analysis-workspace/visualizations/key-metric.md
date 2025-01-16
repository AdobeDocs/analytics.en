---
description: Use the key metric summary visualization to compare metric performance across two timelines.
title: Key metric summary
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
---
# Key metric summary {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Key metric summary"
>abstract="Create a visualization that is a combination of the line, summary change, and summary number charts. Use this visualization to compare how important metrics are trending between two periods of time."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*This article documents the Key metric summary visualization in **Adobe Analytics**.<br/>See [Key metric summary](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/key-metric) for the **Customer Journey Analytics** version of this article.*

>[!ENDSHADEBOX]

The [!UICONTROL Key metric summary] visualization lets you see how an important metric is trending within a single timeframe. It also lets you compare metric performance across two timeframes. It provides the benefits of multiple visualizations combined into one visualization:

* **[!UICONTROL Line]** visualizations that show how the metric is trending for the primary and comparison date ranges

* **[!UICONTROL Summary percent change]** that shows the metric increase or decrease between the primary and comparison date ranges

* Current total value ([!UICONTROL **summary number**]) for the metric

## Use cases

This visualization addresses various common use cases, including:

* An analyst trying to understand how opportunity creation looked this month compared to the same timeframe last year. 

* A marketer exploring how lead generation for a specific lead type has changed from this month to last month.

* An executive wanting to understand how new bookings changed from this quarter to last quarter.

## Configure the Key metric summary

1. Drag the **[!UICONTROL Key metric summary]** visualization from the **[!UICONTROL Visualizations]** menu in the left rail into a panel.

   ![](assets/key-metric-config.png)

1. Configure the visualization with the following options:

   | Configuration setting | Definition |
   | --- | --- |
   | **[!UICONTROL Metric]** | Select the metric you want to examine. All metrics are supported. |
   | **[!UICONTROL Primary date range]** | The current date range for the freeform table.<p>Choose from any available date ranges in your report suite.</p> <p>Choose [!UICONTROL **Panel date range**] if you want to use the same date range that is being used on the panel where the visualization is located.</p> |
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

## View the output

The output should look something like this:

![](assets/key-metric-output.png)

Consider the following when viewing the output:

* The **[!UICONTROL Previous period]** line graph (always displayed in gray) corresponds to the **[!UICONTROL Comparison date range]** in the configuration step.

* If a comparison date range is not specified during configuration or is hidden in the visualization settings, only the line graph for the primary date range is displayed. The summary change is hidden.

* From here, you can hover over the line graphs to see the statistics for individual days:

![](assets/key-metric-output2.png)

## Visualization settings

The Key metric summary offers multiple flexible settings to enable better reporting and communication of important metrics. Settings can be accessed through the gear icon in the top right-hand corner of the visualization.  

![](assets/key-metric-settings.png)

| Setting | Description |
| --- | --- |
| **[!UICONTROL Emphasize percent change]** | Display summary change in prominent bold type in the center of the visualization |
| **[!UICONTROL Emphasize number value]** | Display summary number in prominent bold type in the center of the visualization |
| **[!UICONTROL Legend visible]** | Show or hide the legend at the bottom of the visualization |
| **[!UICONTROL Show annotations]** | Show or hide annotations added by an admin |
| **[!UICONTROL Show sparklines]** | Show or hide line charts at the bottom of the chart. When hidden, the legend changes to no longer visually reference the lines |
| **[!UICONTROL Show min and max on sparklines]** | Show or hide minimum and maximum values on primary and comparison line charts |
| **[!UICONTROL Show comparison]** | Show or hide comparison data. When hidden, both the comparison line chart and summary change objects are hidden from view. |
| **[!UICONTROL Show total number]** | Show or hide summary number |
| **[!UICONTROL Show raw difference]** | Show or hide raw difference between the total value of the metric in the primary date range and the secondary date range |
| **[!UICONTROL Abbreviate value]** | Abbreviate number values to simplify communicated insights (for example, 20,000 -> 20K) |

## Edit visualization

After building the visualization, you can still edit the original configuration. 

1. Click the pencil icon in the top-right corner of the visualization (next to the settings gear icon).

   ![](assets/edit-icon.png)

   You are now taken back to the original configuration view. 

1. Change the metric, primary date range, comparison date range, or segment as preferred.
