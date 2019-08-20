---
description: You can schedule reports to send according to the time and file format that you define.
seo-description: You can schedule reports to send according to the time and file format that you define.
seo-title: Schedule a data request
solution: Analytics
title: Schedule a data request
topic: Report builder
uuid: f6d8c90f-e185-4d60-8035-f20f74bfcd89
---

# Schedule a workbook

You can schedule workbooks, specify advanced delivery options, specify recipients, and view the schedule history. Advanced delivery options let you configure workbooks that you want to send at a specific time or in intervals. You can also specify the file format in which to send the workbook.

For example, you can schedule workbooks to be delivered immediately or on a recurring schedule, and specify the file format in [!DNL Advanced Delivery Options]. The file size limit is 5 MB for a workbook upload.

Additionally, after you create a workbook schedule in Report Builder, you can view and edit the schedule in **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**. (See [Report Schedule and Distribution](/help/analyze/reports-analytics/scheduling.md) in Reports & Analytics help.)

>[!NOTE]
>
>You must have Excel 2007 or the compatibility pack installed in order to schedule a workbook. You can have a maximum of 10 scheduled workbooks per Report Builder license. However, you can increase this number by subtracting from other licenses. To do so, go to **[!UICONTROL Admin]** > **[!UICONTROL Company Settings]** > **[!UICONTROL Report Builder Reports]**. A workbook that has been scheduled (or uploaded to the Workbook Library) and has not been touched (updated, replaced) in more than 28 months will be deleted.

>[!NOTE]
>
>The "Delivery Time"/"Time of Day" entered by the user specifies the time that the workbook should begin processing, not the time that it will actually be delivered. The actual time that the workbook will be delivered is based primarily on how long it takes to process (complex and large workbooks take longer to process than simpler workbooks). For example, if a workbook takes 15 minutes to process, then the actual delivery time will be at least 15 minutes past the originally specified "Delivery Time"/"Time of Day". 
>In addition, there are a number of other factors that can further increase the delay before the workbook is actually delivered:
>
> * **Running many different schedules of the same type at the same time** can overload the system. The Scheduling system only allows a few (5-10) workbooks of any one type to run concurrently, so when more than 5-10 are all scheduled at once, some will need to wait in line for other workbooks to finish before they can begin processing. This issue can be mitigated by scheduling a company's workbooks at staggered times throughout the day or hour, rather than simultaneously.
> * Aside from the specific workbook type, workbooks will also wait in line if the company has **more than 15-20 of any type of workbook scheduled at once (across all different workbook types)**. This can be mitigated by staggering schedule times instead of having many run at the exact same time.
> * **Issues in downstream services** that the Scheduler relies on can also affect delivery of workbooks. For example, if you are independently using the APIs to run workbooks and fill up the API request queue, then your scheduled workbooks may deliver slowly while you compete for that resource.
> * **Report suite latency** (a delay in data collection) can also delay some scheduled workbooks.

 **To schedule a workbook** 

1. Generate and save a workbook.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   The [!UICONTROL Scheduled Reports] tab summarizes all the tasks you have created, as well as the number of remaining tasks. 
1. On the **[!UICONTROL Scheduled Reports]** tab, click **[!UICONTROL New]**.
1. The Basic Scheduling Wizard displays:

   ![](assets/simple-schedule-wizard.png)

1. In the [!UICONTROL Basic Scheduling Wizard], configure the following options:

* **Select Report**: The name of the workbook. For new scheduled workbooks, this field is populated with the active workbook name.

<table id="table_6D5B1B832EB0451293F1902E2A1D1068"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Select Report </p> </td> 
   <td colname="col2"> <p>The name of the report. For new scheduled reports, this field is populated with the active workbook name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Select </p> </td> 
   <td colname="col2"> <p>Displays the <span class="wintitle"> Select Report</span> page. You can select a report from the server (where all your previously scheduled workbooks are stored), or from your local machine. If you select a workbook from the local drive in <span class="filepath"> .xls</span> format, the system converts the file to <span class="filepath"> .xlsx</span>. As part of that conversion, the file is opened in Excel and made active. If the selected workbook for the scheduled report has the same filename as the workbook currently open in Excel, the system selects the local file instead of the previously uploaded file. If you select a report from the scheduling repository, a copy of the workbook is created on the server, with its filename updated with 1, and the newly created scheduled report uses the copied workbook. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Customize </p> </td> 
   <td colname="col2"> <p>Lets you customize the date format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>To </p> </td> 
   <td colname="col2"> <p>Displays your Outlook Address Book, if applicable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Send to: Email </p> </td> 
   <td colname="col2"> <p>The email recipient of the workbook. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Send to: Publishing List </p> </td> 
   <td colname="col2"> <p>Displays a list of available distribution lists for this company. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Power BI </p> </td> 
   <td colname="col2"> <p>See <a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local"> Publish Workbook to Microsoft Power BI</a> for more information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Subject </p> </td> 
   <td colname="col2"> <p>A user-defined description. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scheduling </p> </td> 
   <td colname="col2"> <p> Lets you specify when to send the workbook. (Immediately, hourly, daily, weekly, monthly, and yearly.) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Advanced Delivery Options]** to configure file and publishing options:

<table id="table_1BA8A5600DE94A33B83B096E69CE15F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Scheduling</b> tab </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Delivery Time </p> </td> 
   <td colname="col2"> <p>Lets you schedule the workbook immediately or for a later time. The time of day is relative to the time zone specified on your computer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recurrence Pattern </p> </td> 
   <td colname="col2"> <p>Sends the workbook based on your selections. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Range of Recurrence </p> </td> 
   <td colname="col2"> <p>Lets you specify when to start and stop receiving the workbook. </p> <p> <p>Note:  Scheduling a workbook on the first day of any current period (week, month, quarter, or year) returns data only for the first day. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>File Options</b> tab </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File Format </p> </td> 
   <td colname="col2"> <p>Lets you select a delivery format of Excel 2007 (<span class="filepath"> .xlsx</span>) or 2003 (<span class="filepath"> .xls</span>), <span class="filepath"> .pdf</span>,<span class="filepath"> .csv,</span><span class="filepath"> .mht</span>,<span class="filepath"> .txt</span>, and<span class="filepath"> .xml</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> File Destination </p> </td> 
   <td colname="col2"> <p> Specifies Email or FTP. The options on the page change depending on your selection. For FTP, you must ensure that the host is available externally. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Publishing List </p> </td> 
   <td colname="col2"> <p> If you send the scheduled workbook to multiple publishing lists, the workbook runs once for each list. Variable report suites are replaced by the report suite assigned to the publishing list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File Contents Language </p> </td> 
   <td colname="col2"> <p>Specifies the language you want to use for the cover letter. You can select Chinese (Simplified or Traditional), German, French, Japanese, Korean, Brazilian Portuguese, or Spanish. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Publishing Options</b> tab </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Publishing to Power BI </p> </td> 
   <td colname="col2"> 
    <ul id="ul_40697E4FB2CE4F34B857FBF153D6D6D5"> 
     <li id="li_023E4750814D415EBC899269C9EA5D46"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local"> Publish Workbook to Power BI</a> </li> 
     <li id="li_9B684BE22AF94ABC903405EE83951A80"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_E48148793E794169B766C73995897B9F" format="dita" scope="local"> Publish All Report Builder Requests as Power BI Datasets</a> </li> 
     <li id="li_7B0BD285BC1749D1B2C65759CA97877B"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_6F8422B90D3F4F7EB5D4C97BFFA807AD" format="dita" scope="local"> Publish All Formatted Tables as Power BI Datasets</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Label this Power BI Report as </p> </td> 
   <td colname="col2"> <p>Labeling details </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   Report Builder displays the scheduled workbook in the [Scheduled Task Manager](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31). 

