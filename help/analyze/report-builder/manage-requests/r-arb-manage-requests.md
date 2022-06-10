---
description: Field descriptions for Manage Requests in Report Builder.
title: Manage requests - definitions
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
feature: Report Builder
role: User, Admin
exl-id: fd8c0145-4c7e-4f07-aa63-656a8a20724c
---
# Manage requests - definitions

Field descriptions for Manage Requests in Report Builder.

## Overview {#section_75C288C945FA4781A4EDF806711A5660}

The [!UICONTROL Request Manager] provides a detailed view of the status of all requests you have built for all sheets or just one sheet of the active workbook. You can also add, edit, refresh, and delete a request (functions typically associated with the [!UICONTROL Request Wizard] and [!UICONTROL Request Manager]) by right-clicking on an available cell in the Excel spreadsheet that contains previous requests.

The [!UICONTROL Request Manager] displays when you click **[!UICONTROL Manage]** ( ![](assets/edit_request.gif) in the Report Builder toolbar.

>[!NOTE]
>
>Adobe Report Builder enforces request dependencies only within the same worksheet, not across worksheets. Restricting to dependencies within a single worksheet ensures timeliness of execution.

## Definitions {#section_FD29D8614DE74F32A0027FA130F40304}

<table id="table_0880204181074BDBBA37E3DF2972A672"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>All Sheets </p> </td> 
   <td colname="col2"> <p>Displays requests from all of the sheets of the active workbook. To view requests from specific sheets, turn off this option. If you turn off this option, you must click on a Sheet tab at the bottom of your Excel report to display the requests associated with that sheet in the <span class="wintitle"> Request Manager</span>. The label next to the checkbox indicates which sheet of the workbook currently has the focus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sheet </p> </td> 
   <td colname="col2"> <p>Displays the name of the sheets in the workbook. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report Suite </p> </td> 
   <td colname="col2"> <p>Displays the name of the report suite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date Range </p> </td> 
   <td colname="col2"> <p>Displays the specified date range of the report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Granularity </p> </td> 
   <td colname="col2"> <p>Specifies the granularity of the request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Last Run </p> </td> 
   <td colname="col2"> <p>Specifies the date the request was last processed by Report Builder. A diagnostic message is also displayed in this table in the <span class="wintitle"> Last Run</span> column, if applicable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Add </p> </td> 
   <td colname="col2"> <p>Displays the Request Wizard dialog. See <a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   > Create a Data Request</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edit </p> </td> 
   <td colname="col2"> <p> (Or Edit Multiple) Edits a selected request. The system displays the <span class="wintitle"> Request Wizard</span> dialog. See <a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   > Edit Multiple Requests</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Delete </p> </td> 
   <td colname="col2"> <p>Deletes requests. You can delete multiple selected requests. You can also delete a request in the list by selecting the request and pressing Delete on your keyboard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Select All </p> </td> 
   <td colname="col2"> <p>Select all requests. The <span class="wintitle"> Request Manager</span> displays the number of requests you have selected at the bottom of the request list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>From Cell </p> </td> 
   <td colname="col2"> <p>Gets data for a request from the worksheet. If a request is associated with the currently selected cell in the active worksheet, the associated request in the list is selected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Refresh </p> </td> 
   <td colname="col2"> <p>Refreshes a single request or a selection of requests. (See <a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   > Refresh a Request</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Refresh List </p> </td> 
   <td colname="col2"> <p>Refreshes all displayed requests. When you refresh all requests, the time to update the information from the server to your report is directly proportional to the complexity of the requests in the report. For very large reports, refreshing all requests may require several minutes. For this reason, you may wish to update the most urgent requests individually, and select <span class="wintitle"> Refresh All</span> at another, less time-crucial moment. </p> <p> <p>Note: It is recommended that you check results often in the <span class="wintitle"> Request Manager</span> if you refresh a worksheet containing multiple requests. If a request failure occurs, the error message in the diagnostic column helps you pinpoint the source of the error. While in most cases an error message is displayed when a request fails, note that occasionally no error message is generated. You may notice that a refresh does not update the data in a cell containing a reference, or that an update removes the data from the cell. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>
