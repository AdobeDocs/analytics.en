---
description: Learn about how to use the Reporting Activity Manager to diagnose and fix capacity issues during peak reporting times.
title: Reporting Activity Manager
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
---
# Reporting Activity Manager

{{release-limited-testing}}

The [!UICONTROL Reporting Activity Manager] lets you see the reporting capacity for each report suite in your organization. It provides you, as an Admin, with detailed visibility into reporting consumption and helps you easily diagnose and fix capacity issues during peak reporting times. 

When your organization reaches reporting request capacity and experiences a degradation in reporting performance, you can self-diagnose reporting issues without intervention from Adobe customer care or engineering. You can easily manage reporting queues within a single interface and immediately act​​ to improve your users' experience. 

This tool:

* Informs you, in real time, about your current reporting capacity across your report suites.
* Provides detailed report query information on current reporting requests, whether queued or in progress.
* Lets you optimize the reporting queue by prioritizing some and canceling other reporting requests to free up capacity. In other words, you can ask in real time: is this report necessary at this time or can I cancel it in favor of more urgent reports?
* Lets you restrict future requests for a specified time period. <!--new-->

## Access the Reporting Activity Manager

Adobe Analytics administrators with [sufficient permissions](#permissions) can access the Reporting Activity Manager.

1. In Adobe Analytics, go to **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

## Permissions

You require the Analytics Product Administrator permission (in Adobe Admin Console) to manage reporting activity.

![permission](/help/admin/admin/assets/rep-mgr-permission.png)

## View the reports queue

When opening the [!UICONTROL Reporting Activity] Manager overview page, you see a list of your enabled base report suites.

![reports queue](/help/admin/admin/assets/reporting-activity1.png)

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

![report suite](/help/admin/admin/assets/indiv-report-ste.png)

### Line graph {#line}

The line graph shows the reporting activity for the selected report suite over the last 2 hours. 

* The x-axis shows the reporting capacity data over the last 2 hours.
* The y-axis shows the reporting usage capacity % for the selected report suite, by minute.
* You can hover over the line chart to view points in time where the usage capacity % represented will be the highest % for that minute.

   ![detail](/help/admin/admin/assets/detail.png)

### Filter

You can filter the table by Application (see list in the table below), by User, and by Project.

![filter](/help/admin/admin/assets/filter.png)

### Summary Numbers {#summary}

![filter](/help/admin/admin/assets/summary_numbers.png)

The Summary Numbers show the following information:

| Summary Number | Description |
| --- | --- |
| [!UICONTROL Users] | The number of users that are currently sending reporting requests to this report suite. |
| [!UICONTROL Projects] | Workspace projects, Report Builder workbooks, etc.  | 
| [!UICONTROL Queries] | The number of queries currently running. |
| [!UICONTROL Average Wait Time] | The average wait time for all running queries.  |
| [!UICONTROL Usage Capacity] | The current usage capacity for this report suite. |

{style="table-layout:auto"}

### Table on report suite details {#details}

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

## Cancel reporting requests {#cancel} 

You can cancel reporting requests in order to fix capacity issues during peak reporting times. 

When you cancel requests, you can also choose to restrict the requests for a given time period.

You can cancel requests in any of the following ways:

* [Cancel specific requests](#cancel-by-request)

* [Cancel requests by user](#cancel-requests-by-user)

* [Cancel requests by project](#cancel-requests-by-project)

### Cancel specific requests

You can choose specific requests that you want to cancel.

1. In Adobe Analytics, go to **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Select the report suite where you want to cancel reporting requests. <!--double-check this step-->

1. Select the [!UICONTROL **Requests**] tab, then select one or more requests.

   <!-- add screenshot -->

1. Select [!UICONTROL **Cancel requests**].

   The [!UICONTROL **Cancel x report requests**] dialog box displays.

1. The Cancellation message field shows the message that displays to users when their requests are cancelled. A default message is provided. You can update the default message to provide additional details.

1. (Optional) To restrict future requests for a given time period, enable the option to [!UICONTROL **Restrict subsequent requests**], then choose from the following options:

   |Option | Function | 
   |---------|----------|
   | [!UICONTROL **User & project**] | Users associated with the selected requests will be temporarily restricted from running reporting requests for the associated projects. |
   | [!UICONTROL **User**] | Users associated with the selected requests will be temporarily restricted from making any reporting requests. | 
   | [!UICONTROL **Project**] | Projects associated with the selected requests will be temporarily restricted from all reporting requests. |
   | [!UICONTROL **Restricted for**] | Choose for how long requests will be restricted. You can choose 1 minute (default), 5 minutes, 10 minutes, 15 minutes, or 30 minutes. <!--double-check this--> <p>You cannot remove a restriction early after it is set.</p>  | 

1. Select [!UICONTROL **Continue with cancellation**].

### Cancel requests by user

You can cancel all requests that are associated with one or more users.

1. In Adobe Analytics, go to **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Select the report suite where you want to cancel reporting requests. <!--double-check this step-->

1. Select the [!UICONTROL **Users**] tab, then select one or more users.

   <!-- add screenshot -->

1. Select [!UICONTROL **Cancel requests**].

   The [!UICONTROL **Cancel x report requests from x users**] dialog box displays.

1. The Cancellation message field shows the message that displays to users when their requests are cancelled. A default message is provided. You can update the default message to provide additional details.

1. (Optional) To restrict future requests for a given time period, enable the option to [!UICONTROL **Restrict subsequent requests**], then choose from the following options:

   |Option | Function | 
   |---------|----------|
   | [!UICONTROL **User & project**] | Selected users will be temporarily restricted from making any reporting requests for the associated projects. |
   | [!UICONTROL **User**] | Selected users will be temporarily restricted from making any reporting requests. | 
   | [!UICONTROL **Project**] | Projects associated with the selected users will be restricted from any reporting requests made by any user. |
   | [!UICONTROL **Restricted for**] | Choose for how long requests will be restricted. You can choose 1 minute (default), 5 minutes, 10 minutes, 15 minutes, or 30 minutes. <!--double-check this--> <p>You cannot remove a restriction early after it is set.</p>  | 

1. Select [!UICONTROL **Continue with cancellation**].

### Cancel requests by project

You can cancel all requests that are associated with one or more projects.

1. In Adobe Analytics, go to **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Select the report suite where you want to cancel reporting requests. <!--double-check this step-->

1. Select the [!UICONTROL **Projects**] tab, then select one or more projects.

   <!-- add screenshot -->

1. Select [!UICONTROL **Cancel requests**].

   The [!UICONTROL **Cancel x report requests from x projects**] dialog box displays.

1. The Cancellation message field shows the message that displays to users when their requests are cancelled. A default message is provided. You can update the default message to provide additional details.

1. (Optional) To restrict future requests for a given time period, enable the option to [!UICONTROL **Restrict subsequent requests**], then choose from the following options:

   |Option | Function | 
   |---------|----------|
   | [!UICONTROL **User & project**] | Selected projects will be temporarily restricted from any reporting requests made by the associated users. |
   | [!UICONTROL **User**] | Users associated with the selected projects will be restricted from making any reporting requests. | 
   | [!UICONTROL **Project**] | Selected projects will be temporarily restricted from any reporting requests made by any user. |
   | [!UICONTROL **Restricted for**] | Choose for how long requests will be restricted. You can choose 1 minute (default), 5 minutes, 10 minutes, 15 minutes, or 30 minutes. <!--double-check this--> <p>You cannot remove a restriction early after it is set.</p>  | 

1. Select [!UICONTROL **Continue with cancellation**].



Application users in Workspace, for example, will see the following notice appear in their projects:

![cancel-user-notice](/help/admin/admin/assets/cancel-user-facing.png)

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
| Can I purchase additional reporting capacity? | This capability will be available in the near future. |

{style="table-layout:auto"}
