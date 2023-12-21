---
description: Steps that describe how to create a Data Warehouse request.
title: Data Warehouse request general settings
feature: Data Warehouse
exl-id: f564d5a9-78a2-431e-987a-78c4b0b9d31e
---
# Data Warehouse request general settings

There are various configuration options available when creating a Data Warehouse request. The following information describes how to configure general settings for the request.

For information about how to begin creating a request, as well as links to other important configuration options, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md). 

To configure general settings for a Data Warehouse request:

1. Begin creating a Data Warehouse request in Adobe Analytics by selecting **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Add**].

   For additional details, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. On the New Data Warehouse request page, select the [!UICONTROL **General settings**] tab.

   ![Report destination tab](assets/dw-general-settings.png)

1. Complete the following fields:

   |Option | Function | 
   |---------|----------|
   | Request name | This name appears on the main Data Warehouse page when managing requests. | 
   | Date ranges | Select the date range to be included in the report. <p>You can choose custom dates, or a preset date range. Preset ranges are relative to the date the report is sent.</p><p>The following preset options are available:</p><ul><li>Today</li><li>Yesterday</li><li>Last 7 days</li><li>Last 30 days</li><li>This week</li><li>Last week</li><li>Last 2 weeks</li><li>Last 3 weeks</li><li>Last 4 weeks</li><li>This month</li><li>Last month</li><li>Last hour</li></ul> | 
   | Granularity | <!--what does this setting do? It's not the schedule/frequency... --> The time granularity. Valid values are None, Hour, Day, Week, Month, Quarter, and Year.<p>Reporting granularity requires additional processing time. If you are reporting monthly granularity for an entire year, your reports process much faster if you submit a report request for each month.</p>| 
   | Make available to users in your organization | All data warehouse requests are visible to you and any system administrators. Enable this option if you want to make the request visible to everyone in your organization. <p>Enabling this option is useful if you want other users in your organization to help create or update the request. | 

   {style="table-layout:auto"}

1. Continue configuring your Data Warehouse request on the [!UICONTROL **Build your report**] tab. For more information, see [Build a report for a Data Warehouse request](/help/export/data-warehouse/create-request/dw-request-build-report.md).
