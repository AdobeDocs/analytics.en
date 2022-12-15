---
description: The Report Suite Usage tab provides server usage data for each report suite in all Login companies tied to your Billing company, for the current usage period.
title: View report suite usage
feature: Server Call Usage
exl-id: bedd4ed8-1c8b-45fd-a059-fed88e9fbe73
---
# View report suite usage

The Report Suite Usage tab provides server usage data for each report suite in all Login companies tied to your Billing company, for the current usage period.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Server Call Usage]** > **[!UICONTROL Report Suite Usage]**

>[!IMPORTANT]
>
>If a report suite is not linked to an Experience Cloud Organization, its usage data is not reflected in this dashboard. Also, a billing ID could be tied to multiple Experience Cloud Orgs; there is not always a 1:1 relationship between an org and a billing ID.

The Report Suite Usage dashboard

* Shows the current usage period's server call usage (All Calls, Primary, Secondary, Mobile Primary, Mobile Secondary) for each report suite in your Experience Cloud organization.
* Shows percentage of overall usage per server call category.
* Is updated daily.
* Is downloadable.
* Lets you access the **[!UICONTROL Manage Alerts]** UI.

![](/help/admin/admin/c-server-call-usage/assets/report-suite-usage.png)

| Column | Definition |
|--- |--- |
|Report Suite Name|Friendly name of the report suite|
|All Calls (% of Total)|All server calls incurred in the current usage period.|
|Primary Calls (%)|All primary server calls (and their percentage of total) incurred in the current usage period.|
|Secondary Calls (%)|All secondary server calls (and their percentage of total) incurred in the current usage period.|
|Mobile Primary (%)|All mobile primary server calls (and their percentage of total) incurred in the current usage period.|
|Mobile Secondary (%)|All mobile secondary server calls (and their percentage of total) incurred in the current usage period.|


## Download Usage Report {#section_D7345660B5E043CD8850954216509A3D}

This option lets you download current usage data, and data from time periods prior to the current usage period (going back to January 2015). The report downloads as a .csv file.

1. Select at least one report suite.
1. Click **[!UICONTROL Download Report]**.

   ![](/help/admin/admin/c-server-call-usage/assets/download_report.png)

| Report Element | Description |
|--- |--- |
|File Name|Hardcoded name: Usage Report `day and time of report creation.csv`|
|Included Report Suites|Any report suites you selected on the Report Server Usage page are included in this list.|
|Included Call Types|Specify any combination of these:  All Calls (Default), Primary, Secondary,  Mobile Primary, Mobile Secondary.|
|Time Range|You can choose the current usage period or specify a custom range.  For a custom range, specify the  Range Start and the  Range End. <br>**Note:** You cannot download usage data prior to January 2015 </br>.|

1. Click **[!UICONTROL Download]**.

Here is a screenshot of what the downloaded .csv file looks like. It includes a column for the report suite ID. The report suite ID specifies a unique ID that can contain only alphanumeric characters. This ID cannot be changed after a report suite is created.

![](/help/admin/admin/c-server-call-usage/assets/download-usage.png)
