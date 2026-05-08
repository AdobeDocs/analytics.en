---
title: Cohort Table Overview
description: Learn how to dig deeper into the data around your audience and break that data into related groups with cohort analysis. Use cohort analysis in Analysis Workspace.
feature: Visualizations
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
---
# Cohort table overview {#cohort-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Cohort table"
>abstract="Create a cohort visualization to group users based on completion of an event and analyze ongoing engagement and churn over time."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Cohort table"
>abstract="Group users based on completion of an event, then analyze their ongoing engagement and churn over time.<br/><br/>**Parameters**<br/>**Inclusion criteria**: The components used to define your initial visitor cohorts.<br/>**Return criteria**: The components used to determine if a visitor has returned."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_This article documents the Cohort table in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_See [Cohort table](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis)  for the_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** version of this article._

>[!ENDSHADEBOX]



A *cohort* is a group of people sharing common characteristics over a specified period. A ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Cohort table]** visualization is useful, for example, when you want to learn how a cohort engages with a brand. You can easily spot changes in trends, then respond accordingly. (Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

After creating a cohort report, you can curate its components (specific dimensions, metrics, and filters), then share the cohort report with anyone. See [Curate and Share](/help/analyze/analysis-workspace/curate-share/curate.md).

Examples of what you can do with a [!UICONTROL Cohort table]:

* Launch campaigns designed to spur a desired action.
* Shift marketing budget at exactly the right time in the customer lifecycle.
* Recognize when to end a trial or an offer to maximize value.
* Gain ideas for A/B testing in areas such as pricing, upgrade path, and so on.

[!UICONTROL Cohort table] is available for all Adobe Analytics customers with access rights to [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cohort analysis in Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] does not support non-filterable metrics (including calculated metrics), non-integer metrics (such as Revenue), or Occurrences. Only metrics that can be used in filters can be used in [!UICONTROL Cohort Analysis], and they can only be incremented 1 at a time. 

Cohort tables in Adobe Analytics support double-based (or any numeric-based) metric. For example, Purchase.Value (a double) can be used as an  Inclusion/Return Metric. In addition, all metrics that are passed into Adobe Experience Platform via the Analytics Source Connector are also doubles.

## Cohort table capabilities

The following sections describe Cohort Analysis features that allow for fine-tuned control over the cohorts you are building.

For more detailed information about creating a cohort and running a [!UICONTROL Cohort Analysis] report, see [Configure a Cohort table](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### Retention table

A [!UICONTROL Retention] cohort table returns persons: each data cell shows the raw number and percentage of persons in the cohort who did the action during that time period. You can include up to 3 metrics and up to 10 filters.

![A Rention cohort report showing the units and percentage of persons in the cohort.](assets/retention-report.png)

### Churn table

A [!UICONTROL Churn] cohort table is the inverse of a retention table and shows the persons who fell out or never met the return criteria for your cohort over time. You can include up to 3 metrics and up to 10 filters.

![A Churn table showing units and percentage of people who didn't meet the return criteria for a cohort.](assets/churn-report.png)

### Rolling calculation

You can calculate retention or churn based on the previous column, not the included column, which is referred to as rolling calculation.

![A Cohort retention report showing calculations based on a previous column of data.](assets/retention-report-rolling.png)

### Latency table

A latency table measures the time that has elapsed before and after the inclusion event occurred. Measuring latency is an excellent tool for pre- and post analysis. The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![A Cohort report showing the elapsed time before and after an event.](assets/retention-report-latency.png)

### Custom dimension cohort

You can create cohorts based on a selected dimension, and not time-based cohorts (which are the default). Use dimensions such as [!UICONTROL City geo], [!UICONTROL Marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension to show how retention changes. Based on the different values of these dimensions.

![A Cohort report showing customized report with selected dimensions not the default time-based cohort.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Configure a Cohort table](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>



<!--
A *`cohort`* is a group of people sharing common characteristics over a specified period. [!UICONTROL Cohort Analysis] is useful, for example, when you want to learn how a cohort engages with a brand. You can easily spot changes in trends, then respond accordingly. (Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

After creating a cohort report, you can curate its components (specific dimensions, metrics, and segments), then share the cohort report with anyone. See [Curate and Share](/help/analyze/analysis-workspace/curate-share/curate.md).

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* Launch campaigns designed to spur a desired action.
* Shift marketing budget at exactly the right time in the customer lifecycle.
* Recognize when to end a trial or an offer, in order to maximize value.
* Gain ideas for A/B testing in areas such as pricing, upgrade path, and so on.

[!UICONTROL Cohort Analysis] is available for all Adobe Analytics customers with access rights to [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cohort analysis in Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/overview-of-cohort-tables-in-analysis-workspace){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] does not support non-segmentable metrics (including calculated metrics), non-integer metrics (such as Revenue), or Occurrences. 
>
>Only metrics that can be used in segments can be used in [!UICONTROL Cohort Analysis], and they can only be incremented by >1 at a time. 

## Cohort Analysis capabilities

The following sections describe Cohort Analysis features that allow for fine-tuned control over the cohorts you are building.

For more detailed information about creating a cohort and running a [!UICONTROL Cohort Analysis] report, see [Configure a Cohort Analysis report](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### [!UICONTROL Retention] Table

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. You can include up to 3 metrics and up to 10 segments.

![](assets/retention-report.png)


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calculate rolling retention](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/calculate-rolling-retention-in-cohort-tables){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



### [!UICONTROL Churn] Table

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. You can include up to 3 metrics and up to 10 segments.

![](assets/churn-report.png)

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Churn analysis](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/churn-analysis-with-cohort-tables){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


### [!UICONTROL Rolling Calculation]

Lets you calculate retention or churn based on the previous column, not the included column.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Table

Measures the time that has elapsed before and after the inclusion event occurred. This is an excellent tool for pre/post analysis. The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension] Cohort

Create cohorts based on a selected dimension, and not time-based cohorts, which are the default. Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

-->
