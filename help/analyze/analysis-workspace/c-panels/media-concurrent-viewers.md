---
title: Media Concurrent Viewers Panel
description: Learn how to use and interpret the Media Concurrent Viewers panel in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: 29575b51-e319-4156-9834-aa0b671afb31
---

# Media concurrent viewers panel {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="Media concurrent viewers"
>abstract="Create a panel to analyze average minute audience for specific content, or over a specific time period."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="Media concurrent viewers"
>abstract="Analyze concurrent viewers over time, view peak concurrency, or break down and compare.<br/><br>**Granularity**: Select time period to view concurrent viewers by.<br/>**Panel summary numbers**:<br/>Option to show summary numbers with date or time details for each line. Maximum will show details for peak concurrency. Minimum will show details for the trough.<br/>**Series breakdown (optional)**: Break down visualization by segments, dimensions, dimension items or date ranges. View up to 10 lines at a time. Breakdowns are limited to a single level."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_This article documents the Media concurrent viewers panel in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics Analytics**._<br/>_See [Media concurrent viewers panel](/help/analyze/analysis-workspace/c-panels/media-concurrent-viewers.md) for the_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** version of this article._

>[!ENDSHADEBOX]


>[!NOTE]
>
>The Media average minute audience panel is available only to customers who have purchased the Adobe Analytics for Streaming Media Add-on. 
>
>Contact your Adobe Sales representative or Adobe account team for more information. 
>

The **[!UICONTROL Media concurrent viewers]** panel enables analysis of concurrent viewers over time, with details on peak concurrency and the ability to break down and compare.

You can analyze concurrent viewers to understand where peak concurrency occurred or where drop-offs happened to provide valuable insight into the quality of content and viewer engagement. And to help with troubleshooting or planning for volume or scale.

In Analysis Workspace, the Concurrent viewers metric is the number of unique persons viewing your media streams at a specific point in time, regardless of the number of sessions.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Media concurrent viewers panel](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/using-panels/media-concurrent-viewers-panel-in-analysis-workspace){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



## Use

To use an **[!UICONTROL Media concurrent viewers]** panel:

1. Create a **[!UICONTROL Media concurrent viewers]** panel. For information about how to create a panel, see [Create a panel](panels.md#create-a-panel).  

1. Ensure you select a report suite for the panel that has components configured from the Adobe Analytics for Streaming Media Add-on.

1. Specify the [input](#panel-input) for the panel.

1. Observe the [output](#panel-output) for the panel.

### Panel input

You can configure the Media concurrent viewers panel using these input settings:

|Setting|Description|
|---|---|
|**[!UICONTROL Panel date range]**|The panel date range default is Today.  You may edit it to view a single day or many months at a time. <br> <br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|**[!UICONTROL Granularity]**|The granularity default is Minute.<br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|**[!UICONTROL Panel summary numbers]**| To see date or time details for concurrent viewers, a summary number is available. The Maximum shows details for peak concurrency. **[!UICONTROL Minimum]** shows details for the trough.  The panel default shows Maximum only, but you can change it to show Minimum or both Maximum and Minimum.<br><br>If you are using breakdowns, a summary number is displayed for each.|
|**[!UICONTROL Series breakdown]**| Optionally, you can break down your visualization by filters, dimensions, dimension items, or date ranges.<br>You may view up to 10 lines at a time. Breakdowns are limited to a single level.<br>When dragging a dimension, the top dimension items are selected automatically based on the selected panel date range.<br>To compare date ranges, drag 2 or more date ranges into the series breakdown filter.|

Here is an example of the panel configured for **[!UICONTROL Minute]** granularity, with **[!UICONTROL Maximum only]** summary numbers. And broken down by **[!UICONTROL Other]**, **[!UICONTROL Table]**, **[!UICONTROL Mobile Phone]**, **[!UICONTROL Gaming Console]**, **[!UICONTROL Media Player]**, **[!UICONTROL Set-top Box]**, **[!UICONTROL Television]**.

![The Media Concurrent Viewers Series breakdown view showing 7 of 10 dimensions, segments or date ranges.](assets/concurrent-viewers-series-breakdown.png)

### Panel output

The Media Concurrent Viewers panel returns a line chart and summary numbers to include details for the maximum and/or minimum concurrent viewers.  At the top of the panel, a summary line is provided to remind you of the panel settings you selected.

At any time, select ![Edit Media concurrent viewers panel](/help/assets/icons/Edit.svg) to edit and rebuild the panel.

If you select a series breakdown, a line on the line chart and a summary number is displayed for each:

![The Media Concurrent Viewers output.](assets/concurrent-viewers-output.png)

### Data source

The only metric that can be used in this panel is **[!UICONTROL Concurrent viewers]**:

|Metric|Description|
|---|---|
|**[!UICONTROL Concurrent viewers]**| The number of unique persons viewing your media streams at a specific point in time, regardless of the number of sessions. |

A Freeform table is not available in this view.  To view the data source, you can download the data source from the line chart visualization context menu and select **[!UICONTROL Download data as CSV]**.  Series breakdowns are included.

![The Concurrent viewers output options with "Download data as CSV" highlighted.](assets/concurrent-viewers-download-csv.png)

## FAQs

|Question|Answer|
|---|---|
|Where is the Freeform table? How can I see the data source?| The Freeform table is not available in this view.  You can download the data source from the line chart context menu and select **[!UICONTROL Download data as CSV]**.|
|Why did my granularity change?|This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.<br><br>When changing from a larger date range to a smaller one, the granularity is updated to the lowest detail allowable once the date range is changed. To view a higher granularity, edit the panel and rebuild.|
|How do I compare video names, filters, content types, and others?|To compare these items in a single visualization, drag filters, dimensions, or specific dimension items in the series breakdown filter.<br><br>The view is limited to 10 breakdowns.  To view more than 10, you must use multiple panels.|
|How do I compare date ranges?|To compare date ranges in a single visualization, use the series breakdowns by dragging 2 or more date ranges.  The date ranges override the panel date range.|
|How do I change the visualization type?|This panel only allows for the line visualization for the time series.|
|Can I run anomaly detection?|No.  Anomaly detection is not available for this panel.|
|Why use unique persons instead of active sessions?|Using unique persons enables removal of unwanted spikes at show boundaries (where sessions are ending and starting at the same time).|
|What does it mean to have concurrent viewers at higher granularity than minute?|With a granularity larger than a minute, concurrent viewers is the sum of unique concurrent viewers for all minutes within that time range.  For example, at hour-level granularity concurrent viewers are the sum of unique concurrent viewers for all minutes within the hour.|
|Does the workspace panel show the same information as the Concurrent Viewers Report?|No.  In Analysis Workspace, the Concurrent viewers metric is defined as the number of unique persons viewing your media stream at a specific point in time. Regardless of the number of sessions.<br><br>This metric is different than Concurrent viewer reporting in the Reports section, which uses Concurrent Active Sessions. Using unique persons accounts for the removal of unwanted peaks at show boundaries (where sessions are ending and starting at the same time).|

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Create a panel](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Media playback time spent panel](media-playback-time-spent.md)
>[Media average minute audience panel](average-minute-audience-panel.md)
>
<!--
# Media Concurrent Viewers panel

Customers who have purchased the Streaming Media Collection Add-on can analyze concurrent viewers to understand where peak concurrency occurred or where drop-offs happened to provide valuable insight into the quality of content and viewer engagement, and to help with troubleshooting or planning for volume or scale.

In Analysis Workspace, Concurrent Viewers is the number of unique visitors viewing your media stream(s) at a specific point in time, regardless of the number of sessions.

The Media Concurrent Viewers panel enables analysis of concurrent viewers over time, with details on peak concurrency and the ability to break down and compare.  To access the Media Concurrent Viewers panel, navigate to a report suite with streaming media components enabled. Then, click the panel icon on the far-left and drag the panel into your Analysis Workspace project.

Here is a video overview of this panel:

>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/using-panels/media-concurrent-viewers-panel-in-analysis-workspace)

## Panel Inputs {#Input}

You can configure the Media Concurrent Viewers panel using these input settings:

|Setting|Description|
|---|---|
|Panel date range|The panel date range default is Today.  You may edit it to view a single day or many months at a time. <br> <br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Granularity|The granularity default is Minute. <br> <br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Panel summary numbers| To see date or time details for concurrent viewers, a summary number is available. The Maximum shows details for peak concurrency. The Minimum shows details for the trough.  The panel default shows Maximum only, but you can change it to show Minimum or both Maximum and Minimum.<br><br>If you are using breakdowns, a summary number is displayed for each.|
|Series breakdown| Optionally, you can break down your visualization by segments, dimensions, dimension items, or date ranges. <br><br>- You may view up to 10 lines at a time. Breakdowns are limited to a single level.<br><br>- When dragging a dimension, the top dimension items will be automatically selected based on the selected panel date range.<br><br>- To compare date ranges, drag 2 or more date ranges into the series breakdown filter.|

### Default view

![Default view](assets/concurrent-viewers-default.png)


### Series breakdown view

![series breakdown view](assets/concurrent-viewers-series-breakdown.png)

## Panel Output {#Output}

The Media Concurrent Viewers panel returns a line chart and summary numbers to include details for the maximum and/or minimum concurrent viewers.  At the top of the panel, a summary line is provided to remind you of the panel settings you selected.

At any time, you can edit and rebuild the panel by clicking the edit pencil on the top right.

If you selected series breakdown, a line on the line chart and a summary number is displayed for each:

![concurrent viewers output](assets/concurrent-viewers-output.png)

### Data Source

The only metric that can be used in this panel is Concurrent Viewers:

|Metric|Description|
|---|---|
|Concurrent Viewers| Number of unique visitors viewing your media stream(s) at a specific point in time, regardless of the number of sessions.<br><br>This is different than Concurrent Viewer reporting in the Reports section, which uses Concurrent Active Sessions.  Using unique visitors accounts for removal of unwanted 'spikes' at show boundaries (where sessions are ending and starting at the same time).|

A Freeform table is not available in this view.  In order to view the data source, you may right-click on the line chart and download as a .csv file.  Series breakdowns will be included.


![concurrent viewers output](assets/concurrent-viewers-download-csv.png)

## FAQs {#FAQ}

|Question|Answer|
|---|---|
|Where is the Freeform table? How can I see the data source?| The Freeform table is not available in this view.  You can download the data source by right-clicking on the line chart and downloading the CSV file.|
|Why did my granularity change?|This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity will be automatically updated to accommodate the full date range.<br><br>When changing from a larger date range to a smaller one, the granularity will be updated to the lowest detail allowable once the date range is changed. To view a higher granularity, edit the panel and rebuild.|
|How do I compare video names, segments, content types, etc?|To compare these in a single visualization, drag segments, dimensions, or specific dimension items in the series breakdown filter.<br><br>The view is limited to 10 breakdowns.  To view more than 10, you must use multiple panels.|
|How do I compare date ranges?|To compare date ranges in a single visualization, use the series breakdowns by dragging 2 or more date ranges.  These date ranges will override the panel date range.|
|How do I change the visualization type?|This panel only allows for the line visualization for the time series.|
|Can I run anomaly detection?|No.  Anomaly detection is not available for this panel.|
|Why use unique visitors instead of active sessions?|Using unique visitors enables removal of unwanted spikes at show boundaries (where sessions are ending and starting at the same time).|
|What does it mean to have concurrent viewers at higher granularity than minute?|With a granularity larger than a minute, concurrent viewers is the sum of unique concurrent viewers for all minutes within that time range.  For example, at hour-level granularity concurrent viewers is the sum of unique concurrent viewers for all minutes within the hour.|
|Does the workspace panel show the same information as the Concurrent Viewers Report?|No.  In Analysis Workspace, Concurrent viewers is defined as the number of unique visitors viewing your media stream at a specific point in time, regardless of the number of sessions.<br><br>This is different than Concurrent Viewer reporting in the Reports section, which uses Concurrent Active Sessions.  Using unique visitors accounts for removal of unwanted spikes at show boundaries—where sessions are ending and starting at the same time.|

-->
