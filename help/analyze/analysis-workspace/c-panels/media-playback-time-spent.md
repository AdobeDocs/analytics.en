---
title: Media Playback Time Spent panel
description: How to use and interpret the Media Playback Time Spent panel in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id:
---
# Media Playback Time Spent panel

Media Analytics customers can analyze playback time spent to understand where peak concurrency occurred or where drop-oﬀs happened to provide valuable insight into the quality of content and viewer engagement, and to help with troubleshooting or planning for volume or scale.

In Analysis Workspace, Playback Time Spent is the amount of time spent viewing your media stream(s) at a specific point in time, and includes pause, buffer, and time to start.

The Media Playback Time Spent panel enables analysis of playback over time, with details on peak concurrency and the ability to break down and compare. To access the Media Playback Time Spent panel, navigate to a report suite with Media Analytics components enabled. Then, click the panel icon on the far-left and drag the panel into your Analysis Workspace project.

This panel also includes new functionality in the calendar that enables you to select and display less than 24 hours. You can do that for the entire panel, or you can create segments using consecutive time periods so you can track viewership lead-in/lead-out across programs or sections of programs. Once you’ve placed at least two of those date segments, you’ll see a radio button option for Date Sequence Display that will either overlay the lines with a common x axis start, or display them in sequence with their specific x axis start.

## Panel Inputs {#Input}

You can configure the Media Playback Time Spent panel using these input settings:

|Setting|Description|
|---|---|
|Panel date range|The panel date range default is Today. You may edit it to view a single day or many months at a time.<br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Granularity|The granularity default is Minute.<br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Panel summary numbers|To see date or time details for playback time spent, a summary number is available. The Maximum shows details for peak concurrency. The Minimum shows details for the trough. Sum adds up the total playback time spent for the selection. The panel default shows Maximum only, but you can change it to show Minimum, Sum, or any combination of the three.<br>If you are using breakdowns, a summary number is displayed for each.|
|Series breakdown|Optionally, you can break down your visualization by segments, dimensions, dimension items, or date ranges.<p>- You may view up to 10 lines at a time. Breakdowns are limited to a single level.</p><p>- When dragging a dimension, the top dimension items will be automatically selected based on the selected panel date range.</p>- To compare date ranges, drag 2 or more date ranges into the series breakdown filter.|
|Time format|You can view the playback time spent in either Hours:Minutes:Seconds (default) or in Minutes (which is displayed in whole numbers, rounded up at .5). |
|Date sequence display|If you’ve placed at least two date range segments as series breakdowns you’ll see the option to select either overlay (default) or sequential. Overlay will display the lines with a common x-axis start so that they run in parallel, while sequential will display the lines with their specific x-axis start. If the data lines up (for example, segment 1 ends at 8:44 pm and segment 2 starts at 8:45 pm), then the lines will show in sequence. |

### Default view

![Default view](assets/mpts_default_view.png)

## Panel Output {#Output}

The Media Playback Time Spent panel returns a line chart and summary numbers to include details for the maximum, minimum, and/or sum of playback time spent. At the top of the panel, a summary line is provided to remind you of the panel settings you selected.

At any time, you can edit and rebuild the panel by clicking the edit pencil on the top right.

If you selected series breakdown, a line on the line chart and a summary number is displayed for each:

![media playback time spent output](assets/mpts_outputs1.png)

### Data Source

The only metric that can be used in this panel is Playback Time Spent.

|Metric|Description|
|---|---|
|Playback Time Spent|Total hours:minutes:seconds (or minutes) of content viewed during the selected granularity including pause, buffer, and time to start.|

## FAQs {#FAQ}

|Question|Answer|
|---|---|
|Where is the Freeform table? How can I see the data source?|<p></p><p>The Freeform table is not available in this view. You can download the data source by right-clicking on the line chart and downloading the CSV ﬁle.</p>|
|<p>Why did my granularity change?</p>|<p>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity will be automatically updated to accommodate the full date range.</p><p></p><p>When changing from a larger date range to a smaller one, the granularity will be updated to the lowest detail allowable once the date range is changed. To view a higher granularity, edit the panel and rebuild.</p>|
|<p></p><p>How do I compare video names, segments, content types, etc?</p>|<p>To compare these in a single visualization, drag segments, dimensions, or speciﬁc dimension items in the series breakdown ﬁlter.</p><p></p><p>The view is limited to 10 breakdowns. To view more than 10, you must use multiple panels.</p>|
|How do I compare date ranges?|To compare date ranges in a single visualization, use the series breakdowns by dragging 2 or more date ranges. These date ranges will override the panel date range.|
|How do I change the visualization type?|<p></p><p>This panel only allows for the line visualization for the time series.</p>|
|Can I run anomaly detection?|<p></p><p>No. Anomaly detection is not available for this panel.</p>|
