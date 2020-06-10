---
description: Analytics for Target (A4T) panel lets you analyze your Adobe Target activities and experiences in Analysis Workspace.
title: Analytics for Target (A4T) panel
---

# Analytics for Target (A4T) panel

>[!IMPORTANT]
>
>**[!UICONTROL Analytics for Target (A4T)]** panel is currently in limited testing. [Learn more]( https://docs.adobe.com/content/help/en/analytics/landing/an-releases.html)

The Analytics for Target (A4T) panel lets you analyze your Adobe Target activities and experiences in Analysis Workspace. It also enables you to see lift & confidence for up to 3 success metrics. To access the A4T Panel, navigate to a report suite with A4T components enabled. Then, click the panel icon on the far left and drag the Analytics for Target panel into your Analysis Workspace Project.

## A4T Panel Builder

You can configure the A4T panel using these settings:

|Setting|Description|
|---|---|
|Target Activity|Select from a list of Target Activities, or drag & drop an activity from the left rail.<br>**Note:** The list is populated with the last 6 months of activities that had at least 1 hit. If you do not see an activity in the list, it may be older than 6 months. It can still be added from the left rail, which has a look-back period of up to 18 months.|
|Control Experience|Select your control experience. You can change it if necessary in the dropdown.|
|Normalizing metric| Choose from Unique Visitors, Visits, or Activity Impressions. Unique visitors is recommended for most analysis use cases.|
|Success metrics| Select up to 3 standard (non-calculated) success events from the drop-downs, or drag & drop metrics from the left rail. Each metric will have a dedicated table and visualization in the rendered panel.|
|Calendar date range| This will auto-populate based on the Activity date range from Adobe Target. You can change it if necessary.|

![](assets/a4t-panel-builder.png)

## A4T Panel Output

The Analytics for Target panel returns a rich set of data and visualizations to help you better understand how your Adobe Target activity and experiences are performing. At the top of the panel, a summary line is provided to remind you of the panel settings you selected. At any time, you can edit the panel by clicking the edit pencil in the top right.

For each success metric you selected, one freeform table and one conversion rate trend will be shown: 

![](assets/a4t-rendered.png)

Each freeform table shows the following metric columns:

|Metric|Description|
|---|---|
|Normalizing metrics| Unique Visitors, Visits, or Activity Impressions.|
|Success metric|The metric selected in the builder|
|Conversion rate|Success metric/Normalizing metric|
|Lift|Compares the conversion rate for each experience against the control experience.<br>**Note:** Lift is a "locked metric" to Target experiences; it cannot be broken down or used with other dimensions.|
|Lift (Lower)|Represents the worst lift a variant experience could have over the control.|
|Lift (Mid)| Represents the midpoint lift a variant experience could have over the control, at a 95% confidence interval. This is "Lift" in Reports & Analytics.|
|Lift (Upper)| Represents the best lift a variant experience could have over the control.|
|Confidence| The students t-test calculates the confidence level, which indicates the likelihood that the results would be duplicated if the test were run again. A fixed conditional formatting range of 75%/85%/95% has been applied to the metric. This formatting can be customized if needed under Column settings. <br>**Note:** Confidence is a "locked metric" to Adobe Target experiences. It cannot be broken down or used with other dimensions.|

Like with any panel in Analysis Workspace, you can continue your analysis by adding additional tables and [visualizations]( https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) that will help you analyze your Adobe Target activities. 

## A4T Panel FAQs

|Question|Answer|
|---|---|
|What activity types are supported in A4T?| [Learn more](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup.html) about what activity types are supported.|
|Are calculated metrics supported in A4T reporting?|No. [Learn more]( https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) about why calculated metrics are unsupported.|
|Why would unique visitors vary between Target and Analytics?|[Learn more]( https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) about variances of unique visitors between products.|

For more information regarding Analytics for Target reporting, visit [A4T reporting]( https://docs.adobe.com/content/help/en/target/using/integrate/a4t/reporting.html)
