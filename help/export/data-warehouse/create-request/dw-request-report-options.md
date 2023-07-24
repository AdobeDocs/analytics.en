---
description: Steps that describe how to create a Data Warehouse request.
title: Configure report options for a Data Warehouse request
feature: Data Warehouse
---
# Configure report options for a Data Warehouse request

There are various configuration options available when creating a Data Warehouse request. The following information describes how to configure report options for the request.

For information about how to begin creating a request, as well as links to other important configuration options, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md). 

1. Begin creating a request in Adobe Analytics by selecting **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Add**].

   For additional details, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. On the [!UICONTROL **Report options**] tab, complete the following fields:

   |Option | Function | 
   |---------|----------|
   | File name | Identifies the report. | 
   | Append report date range to file name | Adds the date range to the report file name. This is especially useful for scheduled reports. |
   | CSV | Delivers reports in a CSV file format for viewing data in a spreadsheet. | 
   | Tableau (TDE) | Delivers reports in a Tableau Data Extract (TDE) file format, which can be used to visualize data and layer in additional data within Tableau. |
   | Send report as compressed file (ZIP) | Delivers reports in a compressed (ZIP) file format. We recommend enabling this option when using email as the [report destination](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). | 
   | Number of rows in the table | The number of rows that can be included in the report. Use 0 to include all rows (this is the default selection). <!-- when would you want to limit the rows? To improve performance? Do we have recommendations? --> | 
   | Comments | Add any comments that you want to be included with the report. Comments appear at the beginning of the report. | 
   | Send manifest file | Includes metadata about the files included in the report.<!-- What kind of metadata is included in the manifest file? --> | 
   | Send digital signature file | Allows report recipients to verify that the file came from Adobe and that it has not been altered. | 
   | Send an empty file when there is not data in the report | Sends a report even when the report contains no data. | 

   {style="table-layout:auto"}

1. Continue configuring your Data Warehouse request on the [!UICONTROL **Scheduling options**] tab. For more information, see [Configure scheduling options for a Data Warehouse request](/help/export/data-warehouse/create-request/dw-request-scheduling.md).