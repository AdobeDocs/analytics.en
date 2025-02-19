---
description: Calculated and Advanced Calculated Metrics are custom metrics that you can create from existing metrics.
keywords: Calculated Metrics;Advanced Calculated Metrics
title: Calculated and Advanced Calculated Metrics
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
---
# Calculated and Advanced calculated metrics

Calculated and advanced calculated metrics are custom metrics that you can create from existing metrics.

Our Calculated Metrics tools offer a highly flexible way of building, managing and curating metrics. They allow you as marketers, product managers and analysts to ask questions of the data without having to change your [!DNL Analytics] implementation. The custom metrics available in each [!DNL Analytics] package are:

* Adobe [!DNL Analytics] Foundation: Calculated 
* [Adobe Analytics Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html): Calculated + Advanced Calculated 
* [Adobe Analytics Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html): Calculated + Advanced Calculated 
* [Adobe Analytics Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html): Calculated + Advanced Calculated

Here is a comparison of calculated metrics and advanced calculated metrics capabilities: 

|  Builder Options  | Calculated metrics  | Advanced calculated metrics  |
|---|---|---|
| [Format types (decimal, time, percent, currency)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)  | Yes  | Yes  |
| [Attribution changes (default, linear, participation, etc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)  | Yes  | Yes  |
| [Metric types (standard, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)  | Yes  | Yes  |
|  Basic operators (add, subtract, multiply, divide)  | Yes  | Yes  |
| [Apply segments](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md)  | No  | Yes  |
| [Basic functions (count, abs value, mean, etc)](/help/components/c-calcmetrics/cm-reference/cm-functions.md)  | No  | Yes  |
| [Advanced functions (regression, if/then, t-score, etc)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md)  | No  | Yes  |

## Capabilities {#section_A0A5C275B68A4D628950BBB0B1EE631F}

You can

* Create metrics across [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Anomaly Detection], and [!UICONTROL Contribution Analysis].
* Create segmented metrics that are derived at report run time, without having to change the implementation. These can be viewed historically because they are based on segments.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calculated metrics](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

* Share metrics across report suites. This means that all newly created metrics apply to all reports suites in the same login company.
* (Advanced calculated metrics only) Segment on metrics. For example, you can create a metric for "New visitors", with a count of people for whom this is the first session. 

* (Advanced calculated metrics only) Incorporate statistical functions to help you better describe your data. For example, you can count the number of items in a report or add in the number of standard deviations for each item.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmented calculated metrics in segments](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Limitations {#section_CB878B02451541D68A68B508D4DBD19A}

Some [!DNL Analytics] features let you use events but not calculated metrics:

* [!UICONTROL Fallout] in [!UICONTROL Analysis Workspace] 
* [!UICONTROL Cohort Analysis] in Analysis Workspace 
* [!UICONTROL Data Warehouse] 
* [!UICONTROL Segments] 
* [!DNL Analytics] for [!DNL Target]

## Tools {#section_D65E9C067E9C45E1A50DD30F50561BB2}

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
|Calculated Metric Builder|<ul><li>Create calculated and advanced calculated metrics using advanced allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|
