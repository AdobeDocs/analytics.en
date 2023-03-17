---
description: Log files to help you see when users log in, their usage, access, report suites, and Admin changes.
title: Logs
feature: Admin Tools
exl-id: 43f79e2a-2cb9-47eb-982a-54714c9cbafc
---
# Logs

Log files to help you see when users log in, their usage, access, report suites, and Admin changes.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Logs]**

## Admin Log {#section_8ADE8A7204A8401C968ABC20AECA381D}

The admin log reports all changes made by administrators in admin tools. The log provides a gateway to user-defined reports from any of the three logs. You can search for events matching your selected criteria over a specified date range.

## Usage and Access Log {#section_6FBAF92D9EA244809C45A78A2F0A7232}

The [!UICONTROL Usage and Access Log] lets you evaluate report usage at the user account level. For example, it tracks open, create, update, unshare and delete actions in Analysis Workspace. This allows for better visibility into who is using Workspace, and how often.

|  Element  | Description  |
|---|---|
|  Date Range  | Specify a date range filter. You can enter a date manually in the format YYYY-MM-DD or click the Calendar icon to select a date.  |
|  Login  | Filter the log by user name.  |
|  IP  | Filter the log by an IP address.  |
|  Report Suite  | Filter the log by a specific report suite ID.  |
|  Event Type  | Filter the log by an event type. Select an event type from the drop-down list. See the complete list of event types below.  |
|  Event  | Filter the log by a word or phrase in the event description.  |
|  Download Report  | Exports the contents of the [!UICONTROL Usage & Access Log] to a tab-delimited file.  |

### Event types

|  Event type  | Description  |
| --- | --- |
| No Category | Could be any event type. |
| Login failed | User login process failed. |
| Login successful | User logged in successfully. |
| Admin Action | An admin action occurred, like editing a report suite, changing company settings, creating a user, etc. |
| Security setting change | A security setting was changed. |
| Report viewed | A Reports & Analytics report was viewed. |
| Report downloaded | A Reports & Analytics report was downloaded. |
| Alert sent | An alert was sent. |
| User Action | User information was edited. |
| Tool viewed | A tool was viewed. |
| Omniture Action | An action was performed by Adobe. |
| Password recovery | A password was recovered. |
| BookMarks | A bookmark was managed. |
| Dashboards | A dashboard was managed. |
| Alerts | An alert was managed. |
| Calendar Events | A calendar event was managed. |
| Targets | A target was managed. |
| Report Settings |  A report setting was managed. |
| Scheduled Reports |  A scheduled report was managed. |
| Exclude by IP | IP setting was changed. |
| Name Pages | Deprecated. |
| Classifications |  A classification was managed. |
| Data Sources |  A data source was managed. |
| Workspace Project | A Workspace project was viewed or edited. |
| Segment | A segment was created/edited. |
| Calculated Metric | A calculated metric was created/edited. |
| Date Range | A date range was created/edited. |
| Virtual Report Suite | A virtual report suite was created/edited. |
| Contribution Analysis | A contribution analysis job was run. |
| Api Method | An API call was made. |


## Report Suite Change Log {#section_3864966639414BBEA871F4D0352F56B6}

The Report Suite Change log displays changes made to your report suites outside of Admin.

Tools that can modify a report suite from outside the [!UICONTROL Admin Tools] include:

* Classifications uploads made in a web browser (Classifications uploads made via FTP are not included in the change log) 
* Changes made in earlier versions.
* Changes made by an account representative or Customer Care using internal tools

|  Element  | Description  |
|---|---|
|  Date Range  | Specify a date range filter. You can enter a date manually in the format YYYY-MM-DD or click the Calendar icon to select a date.  |
|  Company  | Filter the log by company name.  |
|  Login  | Filter the log by user name.  |
|  IP  | Filter the log by an IP address.  |
|  Event  | Filter the log by a word or phrase in the event description.  |
|  Download Report  | Exports the contents of the [!UICONTROL Usage & Access Log] to a tab-delimited file.  |
