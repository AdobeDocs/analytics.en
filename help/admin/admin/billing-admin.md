---
description: The Billing page lets you access billing information, including traffic details for each report suite. Only an authorized administrator has access to this page.
title: Billing
feature: Admin Tools
exl-id: cea802e4-99c4-491e-99c2-8476870001f7
---
# Billing

The Billing page lets you access billing information, including traffic details for each report suite. Only an authorized administrator has access to this page.

>[!NOTE]
>
>If access to the billing tab is disabled for your company, contact your Account Manager.

The traffic overview data from the billing page lets you correlate page view data in reports with billable server calls on your invoice. The [!UICONTROL Billing] page lets you do the following:

* Audit your invoice.
* Break down costs by report suite for internal accounting allocations.
* View the distribution of primary and secondary server calls.

The [!UICONTROL Billing] page organizes information by month.

To view monthly traffic overview data, locate the month where you want to view traffic data, then click **[!UICONTROL View]**.

The resulting [!UICONTROL Monthly Invoice] report includes the following information: 

| Column  | Description  |
|--- |--- |
|Report Suite|The report suite involved in the data collection activity.|
|Location|The data center that stores the report suite data: San Jose (California), Dallas (Texas), Pacific Northwest (US), London (UK), or Singapore. In most cases, all company report suites are located in the same data center.|
|Primary Server Calls|Requests received directly from website visitor browsers or the Data Insertion API. Includes Primary Hits (Page Views), Primary Custom Events, Primary Download Events, and Primary Exit Events.|
|Secondary Server Calls|Copies of primary server calls created by multi-suite tags or copied/moved by a VISTA rule.  If a secondary server call has been moved (not copied) to a different report suite by a VISTA rule, the  Billing page identifies this transfer with a negative number. In this case, the accumulated secondary calls are deducted from the primary server calls.|
|Total Server Calls|The combined total of primary and secondary server calls for this report suite at the given location.|
|Page Views|Page view totals for each report suite. You can confirm page view values in   Site Metrics >  Page Views.|
|Downloads|Download totals for each report suite. You can confirm the download values in  Site Content >  Links >  File Downloads.|
|Custom Links|Custom link totals for each report suite. You can confirm the custom link values in  Site Content >  Links >  Custom Links.|
|Exit Links|Exit link totals for each report suite. You can confirm the exit link values in  Site Content >  Links >  Exit Links.|

>[!NOTE]
>
>To obtain a working copy of the [!UICONTROL Monthly Invoice] report, copy it onto your clipboard, then paste it into a spreadsheet program such as Microsoft Excel&#42;.

## Reporting Date vs. Processing Date {#section_51A48C2F223F4904BE1407C13333C457}

In the reporting user interface, the data presented is always attached to the **Reporting Date**, which is the timestamp that is attached to the event.

Usage/Billing, on the other hand, always uses the **Processing Date**, or when the data was actually processed in the system. Due to basic latency, data imports, or event time zone differences (everything is processed in Pacific Time) the Reporting Date and Processing Date do not typically match up completely.
