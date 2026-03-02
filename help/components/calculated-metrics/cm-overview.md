---
description: Learn about calculated metrics that you can create from existing metrics.
keywords: Calculated Metrics
title: Calculated Metrics Overview
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
---
# Calculated metrics overview

Calculated are custom metrics that you can create from existing metrics.

Calculated metric are custom metrics that you can create from existing metrics. Calculated metrics offer a flexible way of to  build, manage, and curate custom metrics that enable you to analyze your data without having to change your implementation.

Calculated metrics are available in each [!DNL Analytics] package, however the Adobe Analytics Foundation Pack for Experience Cloud is limited to basic calculated metrics including [format types (decimal, time, percent, currency)](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md), [allocation changes (default, linear, participation, etc.)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md), [metric types (standard, total)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md), and [basic operators](workflow/c-build-metrics/cm-build-metrics.md#operators) (add, subtract, multiply, and divide).


See the [Adobe Analytics Product Description](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics.html) for more information. 

<!--
Here is a comparison of calculated metrics and advanced calculated metrics capabilities: 

| [Format types (decimal, time, percent, currency)](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Attribution changes (default, linear, participation, etc.)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Metric types (standard, total)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
|  Basic operators (add, subtract, multiply, divide)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Apply segments](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md)  | ![StopCircle](/help/assets/icons/StopCircle.svg)  | Yes  |
| [Basic functions (count, abs value, mean, etc)](/help/components/calculated-metrics/cm-reference/cm-functions.md)  | No  | Yes  |
| [Advanced functions (regression, if/then, t-score, etc)](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)  | No  | Yes  |

-->

## Capabilities {#section_A0A5C275B68A4D628950BBB0B1EE631F}

You can

* [Create metrics](/help/components/calculated-metrics/workflow/cm-workflow.md) across [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Anomaly Detection], and [!UICONTROL Contribution Analysis].
* [Create segmented metrics](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md) that are derived at report run time, without having to change the implementation. For example, you can create a metric for *New visitors*, with a count of people for whom this is the first session.

* [Share metrics](/help/components/calculated-metrics/workflow/cm-sharing.md) across report suites. This means that all newly created metrics apply to all reports suites in the same login company.

* [Incorporate statistical functions](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md) to help you better describe your data. For example, you can count the number of items in a report or add in the number of standard deviations for each item.

## Limitations

Some [!DNL Analytics] features do not allow the use of calculated metrics:

* [!UICONTROL Fallout] in [!UICONTROL Analysis Workspace] 
* [!UICONTROL Cohort Analysis] in Analysis Workspace 
* [!UICONTROL Data Warehouse] 
* [!UICONTROL Segments] 
* [!DNL Analytics] for [!DNL Target]


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calculated metrics](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmented calculated metrics in segments](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-segmented-metrics){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->

>[!MORELIKETHIS]
>
>[Create metrics](/help/components/calculated-metrics/workflow/cm-workflow.md)
>[Build metrics](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)
>[Use functions](/help/components/calculated-metrics/workflow/c-build-metrics/cm-using-functions.md)
>
