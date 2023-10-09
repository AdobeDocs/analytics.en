---
description: Learn about how to use the Reporting Activity Manager to diagnose and fix capacity issues during peak reporting times.
title: Reporting Activity Manager
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
---
# View reporting activity in the Reporting Activity Manager

{{release-limited-testing}}

The [!UICONTROL Reporting Activity Manager] enables administrators to quickly diagnose and fix reporting capacity issues during peak reporting times.

For more information about Reporting Activity manager, including key benefits and permission requirements, see [Reporting Activity Manager overview](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## View reporting activity for all report suites {#view-all-report-suites}

1. In Adobe Analytics, go to **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

   A list of your enabled base report suites is displayed.

   ![reports queue](/help/admin/admin/assets/reporting-activity1.png)

1. (Optional) You can search or filter the list of report suites:

   * Use the search field to search for a specific report suite. Begin typing the report suite name or ID and the list of report suites updates as you type.

   * Select the [!UICONTROL **Filter**] icon ![Filter icon](assets/filter-icon.png) to expand the list of filter options. You can filter by [!UICONTROL **Favorites**] or [!UICONTROL **Status**].

     To mark a report suite as a favorite, select the star icon to the left of the report suite name.

<!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. View utilization information about each report suite. You can select a column header to sort the table by  that column. 

   The following columns are available: 

   | UI Element | Description |
   | --- | --- |
   | **[!UICONTROL Report Suite]** | The base report suite whose reporting activity you are monitoring.|
   |  **[!UICONTROL Virtual report suites]** | Shows all virtual report suites that feed into this base report suite. Virtual report suites add complexity to reporting requests due to additional levels of applied filtering and segmentation. All requests that are coming from the virtual report suites are combined and come down to the base report suite.<p>For example, f you have 10 requests coming from 5 VRSs, that's 50 requests at the base level report suite. This way, you can very quickly hit capacity. |
   | **[!UICONTROL Capacity utilization]** | The percentage of the report suite's reporting capacity that is being used, in real time. <p>**Note** Even a usage capacity that is at 100% doesn't necessarily mean that you should start cancelling reporting requests. 100% usage capacity can be healthy if the average wait time is reasonable. 100% usage capacity could indicate a problem if the number of queued requests is also growing.</p> |
   | **[!UICONTROL Queued requests]** | The number of requests waiting to be processed. <!-- ??? --> |
   | **[!UICONTROL Queue wait time]** | The average wait time for each request to process. <!-- ???? --> |
   | **[!UICONTROL Status]** | The possible statuses are: <ul><li>[!UICONTROL **Active**] (blue): Reports have been run on the report suite and it is being monitored for activity.</li><li>[!UICONTROL **Inactive**] (gray): No reports have ever been run on the report suite. This status is shown only when report suites are first created.</li></ul> |

   {style="table-layout:auto"}

## View reporting activity for a single report suite

1. In Adobe Analytics, select [!UICONTROL **Admin**] > [!UICONTROL **Reporting Activity Manager**].

1. Select the linked title of the report suite for which you want to view details.

   Reporting activity data is displayed for the report suite that you selected.
   
   <!-- Need to update this screenshot: ![report suite](assets/indiv-report-ste.png) -->

1. Use the available graphs and table to understand reporting activity in the report suite.

   * [View graphs](#view-graphs)

   * [View table](#view-data-in-the-table)

### View graphs

The following graphs are available to help you better understand the activity happening in the report suite. If graphs are not visible, select the [!UICONTROL **Show graphs**] button.

#### Utilization graph {#utilization}

The Utilization graph shows how the reporting utilization for the selected report suite over the last 2 hours. 

* The x-axis shows the reporting usage capacity over the last 2 hours.
* The y-axis shows the reporting usage capacity percentage, by minute.
* You can hover over the chart to view points in time where the usage capacity percentage was highest for that minute.

   ![utilization graph](assets/utilization-graph.png)

#### Distinct Users graph

The Distinct Users graph shows the reporting activity for the selected report suite over the last 2 hours. 

* The x-axis shows a 2-hour time frame.
* The y-axis shows the number of users who have made reporting requests, by minute.
* You can hover over the chart to view points in time where the maximum number of users was highest for that minute.

   ![Distinct Users graph](assets/distinct-users-graph.png)

<!--

#### Requests graph

The Requests graph shows the number of processed and completed requests for the selected report suite over the last 2 hours. 

* The x-axis shows a 2-hour time frame.
* The y-axis shows the number of processed requests (in purple) and completed requests (in green), by minute.
* You can hover over the chart to view points in time where the maximum number of requests was highest for that minute.

   ![Distinct Users graph](assets/requests-graph.png)

#### Queueing graph

The Queueing graph shows the average queue wait time (in seconds) for reporting requests for the selected report suite over the last 2 hours. 

* The x-axis shows a 2-hour time frame.
* The y-axis shows the average wait time (in seconds).
* You can hover over the chart to view points in time where the maximum average wait time was highest for that minute.

   ![Distinct Users graph](assets/queueing-graph.png)

-->

### View table {#view-table}

You can choose to view data by choosing any of the following tabs at the top of the data table: [!UICONTROL **Request**], [!UICONTROL **User**], [!UICONTROL **Project**], or [!UICONTROL **Application**].

>[!TIP]
>
>You can select [!UICONTROL **Hide graphs**] to show only the table.

![table tabs](assets/indiv-report-ste-table-tabs.png)

#### View data by request

When you select the [!UICONTROL **Request**] tab, the following columns are available in the table:

| Column | Description |
| --- | --- |
| [!UICONTROL **Request ID**] | Can be used for troubleshooting purposes. |
| [!UICONTROL **Time run**] | How long the request has been running. |
| [!UICONTROL **Start time**] | When the request started processing (based on the administrator's local time). |
| [!UICONTROL **Wait time**] | How long the request has been waiting before being processed. Generally at "0" when there is enough capacity. |
| [!UICONTROL **Application**] | The applications supported by the [!UICONTROL Reporting Activity Manager] are: <ul><li>Analysis Workspace UI</li><li>Workspace scheduled projects</li><li>Report Builder</li><li>Builder UIs: Segment, Calculated Metrics, Annotations, Audiences, etc.</li><li>API calls from 1.4 or 2.0 API</li><li>Intelligent alerts</li></ul> |
| [!UICONTROL **User**] | The user who initiated the request. If the value of this column is [!UICONTROL **Unrecognized**], this means that the user is in a login company where you do not have administrative permissions. |
| [!UICONTROL **Project**] | Saved Workspace project names, API Report ID's, etc. (Metadata can vary across various applications.) |
| [!UICONTROL **Status**] | Status indicators: <ul><li>**Running**: Request is currently being processed.</li><li>**Pending**: Request is waiting to be processed.</li></ul> |
| [!UICONTROL **Complexity**] | Gives a general idea about the resources required to process the request. Possible values include: <ul><li>[!UICONTROL **Low**]</li><li>[!UICONTROL **Medium**]</li><li>[!UICONTROL **High**]</li></ul>This value is based on a score that is determined by the values in the following columns:<ul><li>[!UICONTROL **Month boundaries**]</li><li>[!UICONTROL **Columns**]</li><li>[!UICONTROL **Segments**]</li></ul> |
| [!UICONTROL **Month Boundaries**] | The number of months that are included in a request. This adds to the complexity of the request. |
| [!UICONTROL **Columns**] | The number of metrics and breakdowns in the request. This adds to the complexity of the request. |
| [!UICONTROL **Segments**] | The number of segments applied to the request. This adds to the complexity of the request. |

{style="table-layout:auto"}

#### View data by user

When you select the [!UICONTROL **User**] tab, the following columns are available in the table:

| Column | Description |
| --- | --- |
| [!UICONTROL **User**] | The user who initiated the request. If the value of this column is [!UICONTROL **Unrecognized**], this means that the user is in a login company where you do not have administrative permissions. |
| [!UICONTROL **Number of requests**] | The number of requests initiated by the user. |
| [!UICONTROL **Number of projects**] | The number of projects associated with the user. <!-- ??? --> |
| [!UICONTROL **Application**] | The applications supported by the [!UICONTROL Reporting Activity Manager] are: <ul><li>Analysis Workspace UI</li><li>Workspace scheduled projects</li><li>Report Builder</li><li>Builder UIs: Segment, Calculated Metrics, Annotations, Audiences, etc.</li><li>API calls from 1.4 or 2.0 API</li><li>Intelligent alerts</li></ul> |
| [!UICONTROL **Avg complexity**] | The value in this column is based on a score that is determined by the values in the following columns:<ul><li>Avg Month Boundaries</li><li>Avg Columns</li><li>Avg Segments</li></ul> |
| [!UICONTROL **Avg Month Boundaries**] | The average number of months that are included in the requests. This adds to the average complexity of the request. |
| [!UICONTROL **Avg Columns**] | The average number of metrics and breakdowns in the included requests. This adds to the average complexity.  |
| [!UICONTROL **Avg Segments**] | The average number of segments applied to the included requests. This adds to the average complexity. |

{style="table-layout:auto"}

#### View data by project

When you select the [!UICONTROL **Project**] tab, the following columns are available in the table:

| Column | Description |
| --- | --- |
| [!UICONTROL **Project**] | The project where the queries were initiated. |
| [!UICONTROL **Number of requests**] | The number of requests associated with the project. |
| [!UICONTROL **Number of users**] | The number of users associated with the project. <!-- ??? --> |
| [!UICONTROL **Application**] | The applications supported by the [!UICONTROL Reporting Activity Manager] are: <ul><li>Analysis Workspace UI</li><li>Workspace scheduled projects</li><li>Report Builder</li><li>Builder UIs: Segment, Calculated Metrics, Annotations, Audiences, etc.</li><li>API calls from 1.4 or 2.0 API</li><li>Intelligent alerts</li></ul> |
| [!UICONTROL **Avg complexity**] | The value in this column is based on a score that is determined by the values in the following columns:<ul><li>Avg Month Boundaries</li><li>Avg Columns</li><li>Avg Segments</li></ul> |
| [!UICONTROL **Avg Month Boundaries**] | The average number of months that are included in the requests. This adds to the average complexity of the request. |
| [!UICONTROL **Avg Columns**] | The average number of metrics and breakdowns in the included requests. This adds to the average complexity. |
| [!UICONTROL **Avg Segments**] | The average number of segments applied to the included requests. This adds to the average complexity. |

{style="table-layout:auto"}

#### View data by application

When you select the [!UICONTROL **Application**] tab, the following columns are available in the table:

| Column | Description |
| --- | --- |
| [!UICONTROL **Application**] | The application where the queries were initiated. |
| [!UICONTROL **Number of requests**] | The number of requests associated with the application. |
| [!UICONTROL **Number of users**] | The number of users associated with the application. <!--???--> |
| [!UICONTROL **Number of projects**] | The number of projects associated with the application. <!--???--> |
| [!UICONTROL **Avg complexity**] | The value in this column is based on a score that is determined by the values in the following columns:<ul><li>Avg Month Boundaries</li><li>Avg Columns</li><li>Avg Segments</li></ul> |
| [!UICONTROL **Avg Month Boundaries**] | The average number of months that are included in the requests. This adds to the average complexity of the request. |
| [!UICONTROL **Avg Columns**] | The average number of metrics and breakdowns in the included requests. This adds to the average complexity. |
| [!UICONTROL **Avg Segments**] | The average number of segments applied to the included requests. This adds to the average complexity. |

{style="table-layout:auto"}

<!--

### Filter

You can filter the table by Application (see list in the table below), by User, and by Project.

![filter](/help/admin/admin/assets/filter.png)

### Summary Numbers {#summary}

![filter](/help/admin/admin/assets/summary_numbers.png)

The Summary Numbers show the following information:

| Summary Number | Description |
| --- | --- |
| [!UICONTROL **Users**] | The number of users that are currently sending reporting requests to this report suite. |
| [!UICONTROL **Projects**] | Workspace projects, Report Builder workbooks, etc.  | 
| [!UICONTROL **Queries**] | The number of queries currently running. |
| [!UICONTROL **Average Wait Time**] | The average wait time for all running queries.  |
| [!UICONTROL **Usage Capacity**] | The current usage capacity for this report suite. |

{style="table-layout:auto"}

-->


