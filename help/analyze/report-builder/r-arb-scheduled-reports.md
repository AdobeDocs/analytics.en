---
description: Field descriptions for the Scheduled Task Manager.
seo-description: Field descriptions for the Scheduled Task Manager.
seo-title: Scheduled Task Manager
solution: Analytics
title: Scheduled Task Manager
topic: Report builder
uuid: dec259f0-2a04-4c94-abbc-5008cf2f1cb8
---

# Scheduled Task Manager

Field descriptions for the Scheduled Task Manager.

The Scheduled Task Manager lets you see a list of existing scheduled reports, along with their recipients, schedule details, and file formats. It also lets you reactivate scheduled workbooks that failed to run. 

<table id="table_21B07A0B5F1D4435A4E882E45A7A6B6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Scheduled Reports </b>tab </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report Name </p> </td> 
   <td colname="col2"> <p>Indicates the name of the scheduled task. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Email/FTP </p> </td> 
   <td colname="col2"> <p>The email or FTP address of the recipient. </p> <p>Note:  If email is selected, reports larger than 1 MB are automatically attached to the email as a .zip file. This feature helps keep attachment file size small and cannot be disabled. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Publishing Options </p> </td> 
   <td colname="col2"> <p>This column will list Power BI if one of the <a href="/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md"  > Power BI publishing options</a> is selected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schedule </p> </td> 
   <td colname="col2"> <p>The type of delivery scheduled. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> File Format </p> </td> 
   <td colname="col2"> <p> The delivery format of the report, such as Excel, PDF, HTML, and so on. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reactivate </p> </td> 
   <td colname="col2"> <p>When a scheduled workbook fails to run, Report Builder attempts to run the workbook two more times every fifteen minutes. After three failed attempts, Report Builder deactivates the schedule and displays the <span class="wintitle"> Reactivate</span> button. When you reactivate a workbook, the scheduled delivery restarts from the time it became deactivated. </p> <p>For example, if a scheduled workbook was deactivated 14 days ago, and you reactivate it today, it runs for every missing day and will be delivered 14 times. If you do not want the workbook delivered for the missing days, you can delete the scheduled workbook and then create a new scheduled workbook using the same scheduling parameters. </p> <p> <p>Note:  You should not reactivate a workbook unless you know the reason the system deactivated it. One troubleshooting solution is to download a deactivated workbook, and refresh it on the client side. If you see no errors, you should be able to reactivate it. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Last sent </p> </td> 
   <td colname="col2"> <p>The date and time when the report was last sent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Recipient </b>tab </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recipient email </p> </td> 
   <td colname="col2"> The email recipient of the report. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reports </p> </td> 
   <td colname="col2"> The report/s that were sent to each recipient. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Reports History</b> tab </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File Name </p> </td> 
   <td colname="col2"> Indicates the name of the scheduled task. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date </p> </td> 
   <td colname="col2"> The date and time when the report was last sent. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> The status indicates whether the report was Sent or Not Sent. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Email/FTP </p> </td> 
   <td colname="col2"> The email or FTP address of the recipient of the report. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File Format </p> </td> 
   <td colname="col2"> The delivery format of the report, such as Excel, PDF, HTML, and so on. </td> 
  </tr> 
 </tbody> 
</table>
