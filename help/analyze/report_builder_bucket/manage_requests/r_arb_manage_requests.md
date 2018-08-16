---
description: Field descriptions for Manage Requests in Report Builder.
seo-description: Field descriptions for Manage Requests in Report Builder.
seo-title: Manage requests - definitions
solution: Analytics
title: Manage requests - definitions
topic: Report builder
uuid: 3266716f-fc8a-442f-aa20-14ed62a883ea
index: y
internal: n
snippet: y
translate: y
---

# Manage requests - definitions


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
   <td colname="col2"> <p>Displays the Request Wizard dialog. See <a href="../../report_builder_bucket/data_requests/t_create_a_data_request.md#task_65B453C8F015429A8EA73A1B64025B6C" type="task" format="dita" scope="local"> Create a Data Request</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edit </p> </td> 
   <td colname="col2"> <p> (Or Edit Multiple) Edits a selected request. The system displays the <span class="wintitle"> Request Wizard</span> dialog. See <a href="../../report_builder_bucket/manage_requests/t_edit_multiple_requests/t_edit_multiple_requests.md#task_70A13DBE43CD4BBEBE1B62459ADB3AD1" type="task" format="dita" scope="local"> Edit Multiple Requests</a>. </p> </td> 
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
   <td colname="col2"> <p>Refreshes a single request or a selection of requests. (See <a href="../../report_builder_bucket/manage_requests/t_refresh_a_request.md#task_96556DB051A2479A955999D3837EE609" type="task" format="dita" scope="local"> Refresh a Request</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Refresh List </p> </td> 
   <td colname="col2"> <p>Refreshes all displayed requests. When you refresh all requests, the time to update the information from the server to your report is directly proportional to the complexity of the requests in the report. For very large reports, refreshing all requests may require several minutes. For this reason, you may wish to update the most urgent requests individually, and select <span class="wintitle"> Refresh All</span> at another, less time-crucial moment. </p> <p> <p>Note: It is recommended that you check results often in the <span class="wintitle"> Request Manager</span> if you refresh a worksheet containing multiple requests. If a request failure occurs, the error message in the diagnostic column helps you pinpoint the source of the error. While in most cases an error message is displayed when a request fails, note that occasionally no error message is generated. You may notice that a refresh does not update the data in a cell containing a reference, or that an update removes the data from the cell. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

