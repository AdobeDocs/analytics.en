---
description: Steps that describe how to create a Data Warehouse request.
title: Configure a report destination for a Data Warehouse request
feature: Data Warehouse
---
# Configure scheduling options for a Data Warehouse request

There are various configuration options available when creating a Data Warehouse request. The following information describes how to configure scheduling options for the request.

For information about how to begin creating a request, as well as links to other important configuration options, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md). 

To configure scheduling options for a Data Warehouse request:

1. Begin creating a request in Adobe Analytics by selecting **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Add**].

   For additional details, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. On the [!UICONTROL **Scheduling options**] tab, complete the following fields:

   |Option | Function | 
   |---------|----------|
   | Send report now | Sends the report as a one-time report. | 
   | Report frequency | The frequency with which reports are delivered. <p>The following options are available:</p><ul><li>Hourly</li><p>[!UICONTROL **Hourly**] is available only when the [!UICONTROL **Date ranges**] option on the [!UICONTROL **General settings**] tab is set to [!UICONTROL **Last hour**].</p><li>Daily</li><li>Weekly</li><li>Monthly</li><li>Yearly</li></ul>  <!-- Is this valid? Was in the old docs: "To schedule Data Warehouse requests for Daily, Weekly, Monthly, or Yearly, make sure *Preset* is correctly selected" -->  | 
   | Monthly recurrence | The interval between months when the report is sent. | 
   | Day of the month | The date each month when the report is sent.<p>When this option is available, the [!UICONTROL **Week of the month**] and [!UICONTROL **Day of the week**] options are not. Select the [!UICONTROL **Alternate format**] button to toggle back and forth. </p> | 
   | Week of the month | The week of each month that the report should be sent. <p>The following options are available:</p><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><p>Send the report on the 4th week, even on months with 5 weeks. Choose [!UICONTROL **Last**] if you want the report sent on the last week of every month.</p><li>Last</li></ul><p>When this option is available, the [!UICONTROL **Day of the month**] option is not. Select the [!UICONTROL **Alternate format**] button to toggle back and forth. </p> | 
   | Day of the week | The day of the week that the report should be sent. <p>When this option is available, the [!UICONTROL **Day of the month**] option is not. Select the [!UICONTROL **Alternate format**] button to toggle back and forth. </p> | 
   | Starting on | The date when the new schedule should start. | 
   | Time of day | The time of day that the report should be sent. | 
   | End delivery options | Choose when to end the scheduled deliveries. You can choose to never end, to end after a specific number of occurrences, or to end on a specific date. | 

   {style="table-layout:auto"}

1. Continue configuring your Data Warehouse request on the [!UICONTROL **Notification email**] tab. For more information, see [Configure a notification email for a Data Warehouse request](/help/export/data-warehouse/create-request/dw-request-email.md).
  