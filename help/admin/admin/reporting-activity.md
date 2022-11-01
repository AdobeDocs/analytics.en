---
description: Learn about how to use the Reporting Activity Manager to diagnose and fix capacity issues during peak reporting times.
title: Reporting Activity Manager
feature: Admin Tools
mini-toc-levels: 3
---

# Reporting Activity Manager

>[!NOTE]
>
>This functionality is currently in beta testing.

The [!UICONTROL Reporting Activity Manager] lets you see the reporting capacity for each report suite in your organization. It provides you, as an Admin, with detailed visibility into reporting consumption and helps you easily diagnose and fix capacity issues during peak reporting times. 

When your organization reaches reporting request capacity and experiences a degradation in reporting performance, you now have a way to self-diagnose reporting issues without intervention from Adobe customer care or engineering. You can easily manage reporting queues within a single interface and immediately act​​ to improve your users' experience. This tool:

* Informs you, in real time, about your current reporting capacity  across your report suites.
* Provides detailed report query information on current reporting requests, whether queued or in progress.
* Lets you optimize the reporting queue by prioritizing some and canceling other reporting requests to free up capacity. In other words, you can ask in real time: is this report necessary at this time or can I cancel it in favor of more urgent reports?

## Access the Reporting Activity Manager

In Adobe Analytics, Admins go to **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

## Permissions

You require Analytics Product Admin permissions to manage reporting activity.

## View the reports queue

When opening the [!UICONTROL Reporting Activity] Manager overview page, you see a list of your enabled base report suites.

![reports queue](assets/reporting-activity1.png)

| UI Element | Description |
| --- | --- |
| **[!UICONTROL Report Suite]** | The base report suite whose reporting activity you are monitoring.|
|  **[!UICONTROL Virtual Report Suite]** | Shows all virtual report suites that feed into this base report suite. Virtual report suites add complexity to reporting requests due to additional levels of applied filtering and segmentation. All requests that are coming from the virtual report suites are combined and come down to the base report suite.<p>For example, f you have 10 requests coming from 5 VRSs, that's 50 requests at the base level report suite. This way, you can very quickly hit capacity. |
| **[!UICONTROL Usage Capacity]** | Percentage wise, how much of the report suite's reporting capacity is being used, in real time. |
| **[!UICONTROL Status]** | Four possible status indicators: <ul><li>**Red - [!UICONTROL At Capacity]**: The report suite is maxed out in terms of reporting capacity. (100%) </li><li>**Yellow - [!UICONTROL Nearing capacity]**: This report suite is in danger of reaching its maximum capacity. (90% - 99%)</li><li>**Green - [!UICONTROL All good]**: There is plenty of reporting capacity. (0% - 89%)</li><li>**Grey - [!UICONTROL Status pending/Not enabled]**: Report capacity not available.</li></ul>|

{style="table-layout:auto"}

### Other Reporting Activity actions

* Click **[!UICONTROL Refresh]** at the top right to refresh the results.
* Click the star to the left of the report suite name to favorite this report suite.
* Check **[!UICONTROL Favorites]** at the top left to show your favorites.
* Search on report suites by name or by ID in the search bar.
* Filter report suites by their status.

## View reporting activity for individual report suites

Click the title link of a report suite for which you want to view details.

![report suite](assets/indiv-report-ste.png)

### Line graph

The line graph shows the reporting activity for the selected report suite over the last 2 hours. 

* The x-axis shows the reporting capacity data over the last 2 hours.
* The y-axis shows the average wait time for a query, in seconds.
* You can hover over the line chart to view points in time and average wait time for that instant.

   ![detail](assets/detail.png)

### Filter

You can filter the table by Application (see list in the table below), by User, and by Project.

![filter](assets/filter.png)

### Summary Numbers

![filter](assets/summary_numbers.png)

The Summary Numbers show the following information:

| Summary Number | Description |
| --- | --- |
| [!UICONTROL Users] | How many users are currently sending reporting requests to this report suite.  |
| [!UICONTROL Projects] | Workspace projects, Report Builder workbooks, etc.  | 
| [!UICONTROL Queries] | The number of queries currently running. |
| [!UICONTROL Average Wait Time] | The average wait time for all running queries.  |
| [!UICONTROL Usage Capacity] | The current usage capacity for this report suite. |

{style="table-layout:auto"}

### Table

The detailed table below shows details on the report suite.

| Column | Description |
| --- | --- |
| [!UICONTROL Query ID] | Can be used for troubleshooting purposes. |
| [!UICONTROL Running Time] | How long the query has been running. |
| [!UICONTROL Wait Time] | How long the query has been waiting before being processed. Generally at "0" when there is enough capacity. |
| [!UICONTROL Start Time] | When the query started processing (Admin's local time). |
| [!UICONTROL Application] | The applications supported by the [!UICONTROL Reporting Activity Manager] are: <ul><li>Analysis Workspace UI</li><li>Workspace scheduled projects</li><li>Report Builder</li><li>Builder UIs: Segment, Calculated Metrics, Annotations, Audiences, etc.</li><li>API calls from 1.4 or 2.0 API</li><li>Intelligent alerts</li></ul> |
| [!UICONTROL User] | The user who initiated the query. |
| [!UICONTROL Project] | Saved Workspace project names, API Report ID's, etc. (Metadata can vary across various applications.) |
| [!UICONTROL Month Boundaries] | How many monthly boundaries a request crosses. This adds to the complexity of the request. |
| [!UICONTROL Columns] | The number of metrics and breakdowns in Workspace to gauge the complexity of the request. |
| [!UICONTROL Segments] | How many segments are applied to this request. This adds to the complexity of the request. |
| [!UICONTROL Status] | Status indicators: <ul><li>**Running**: Request is currently being processed.</li><li>**Pending**: Request is waiting to be processed.</li></ul> |

{style="table-layout:auto"}

## Cancel reporting requests

To cancel a request 

1. Check the box to the left of one or more **[!UICONTROL Query ID]** in the table and click **[!UICONTROL Cancel requests]** at the bottom. (You can also cancel requests in bulk by viewing details by [!UICONTROL User], [!UICONTROL Project], or [!UICONTROL Application].)
1. In the **[!UICONTROL Cancel x query]** window that appears, you can modify the cancellation message, if needed.
1. Click **[!UICONTROL Continue]**.

   ![cancel-query](assets/cancel-query.png)

Application users in Workspace, for example, will see the following notice appear in their projects:

![cancel-user-notice](assets/cancel-user-facing.png)

## Frequently asked questions

| Question | Answer |
| --- | --- |
| Can I purchase additional reporting capacity? | This capability will be available in the near future. |

{style="table-layout:auto"}
