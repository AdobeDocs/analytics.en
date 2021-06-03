---
description: On the Options panel, you can specify the date settings, latency settings (Current Data), log information, and configure updates.
title: Report Builder options
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
feature: Report Builder
role: Business Practitioner, Administrator
exl-id: d3388990-7919-461d-a96e-4c996b8bdb8b
---
# Report Builder options

On the Options panel, you can specify the date settings, latency settings (Current Data), log information, and configure updates.

1. In the Add-Ins toolbar, click **[!UICONTROL Options]** ![](assets/options_icon.png):

| Element | Description |
|--- |--- |
|[!UICONTROL As Of Date]||
|Set to current date|Lets you specify or reset the  [!UICONTROL As Of Date] so that report builder uses the current date or asks you which date to use upon refresh.|
|Ask me to set upon refresh|Lets you set the  [!UICONTROL As Of Date] when refreshing a request.|
|[!UICONTROL Data Recency]||
|[!UICONTROL Include Current Data]|Lets you view data latency (also known as  [!UICONTROL Data Recency]) down to the minute in reporting, occasionally even before this data has been processed by  Adobe Analytics.<br>When you do not use this option,  finalized mode (processed) is used, which is typically more [latent](https://experienceleague.adobe.com/docs/ analytics/analyze/reports-analytics/current-data.html).<br>This setting applies to all requests in the workbook that are compatible Current Data. If the request is not compatible, the finalized mode is applied.<br>Note the following situations for using the [!UICONTROL Include Current Data] mode:<br>**Format Options**: You can specify whether to display this information ([!UICONTROL Data Recency]) when [formatting display headers](/help/analyze/report-builder/layout/t-format-display-headers.md).<br>**Breakdowns**: Not supported. If the  [!UICONTROL Data Recency] mode is set to the Current Data, and one of the requests contains a break-down element, this request reverts to non-current data mode. Other requests, however, continue to use Current Data mode.<br>**Request Manager**: You can view a Current Data column in the Request Manager, so that you can see if the setting is applied to a scheduled request.<br>**Scheduled Workbooks**: This mode is stored during the scheduling process at the workbook level. If you open a scheduled workbook that is using finalized data, and apply [!UICONTROL Include Current Data], current mode is used thereafter.<br>**Permissions**: For users who do not have access to current data, this option is hidden.  When enabling this option, if one or more requests cannot be applied, a warning is issued.|
|Disable Current Data incompatible request warnings|Displays warnings if the  [!UICONTROL Include Current Data] mode is selected but the data mode cannot be applied to the edited request.  For example, if you set [!UICONTROL Include Current Data], and then edit a request that has a segment selected, a warning is issued.|
|Log report builder requests to local file (for troubleshooting)|Lets you log requests to a local file. Use this log file for troubleshooting.|
|Interpret typed value...|Interprets a typed value in a filter control as a cell location before considering it a filter expression.<br>For example if you create a Top 10 Page request, using a filter  shoes, the request would display a cell containing something similar to:   Filter: Top 1-10 Page, Page contains Shoes|
|Update when a new version is available|Tells the system to notify you if a new version is available for installation.|
