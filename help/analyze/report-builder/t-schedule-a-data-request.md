---
description: Learn how to schedule reports.
title: How to schedule a data request
uuid: f6d8c90f-e185-4d60-8035-f20f74bfcd89
feature: Report Builder
role: User, Admin
exl-id: 6aaadaa8-d68f-4a03-8838-53a61b152e31
---
# Schedule workbooks

You can schedule workbooks, specify advanced delivery options, specify recipients, and view the schedule history. Advanced delivery options let you configure workbooks that you want to send at a specific time or in intervals. You can also specify the file format in which to send the workbook.

For example, you can schedule workbooks to be delivered immediately or on a recurring schedule, and specify the file format in [!DNL Advanced Delivery Options]. The file size limit is 5 MB for a workbook upload.

Additionally, after you create a workbook schedule in Report Builder, you can view and edit the schedule in **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**. (See [Report Schedule and Distribution](/help/analyze/reports-analytics/scheduling.md) in Reports & Analytics help.)

>[!NOTE]
>
>You must have Excel 2007 or the compatibility pack installed in order to schedule a workbook. You can have a maximum of 10 scheduled workbooks per Report Builder license. However, you can increase this number by subtracting from other licenses. To do so, go to **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Company settings]** > **[!UICONTROL Report Builder Reports]**. A workbook that has been scheduled (or uploaded to the Workbook Library) and has not been touched (updated, replaced) in more than 28 months will be deleted.

>[!NOTE]
>
>The "Delivery Time"/"Time of Day" entered by the user specifies the time that the workbook should begin processing, not the time that it will actually be delivered. The actual time that the workbook will be delivered is based primarily on how long it takes to process (complex and large workbooks take longer to process than simpler workbooks). For example, if a workbook takes 15 minutes to process, then the actual delivery time will be at least 15 minutes past the originally specified "Delivery Time"/"Time of Day".
>In addition, there are a number of other factors that can further increase the delay before the workbook is actually delivered:
>
> * **Running many different schedules of the same type at the same time** can overload the system. The Scheduling system only allows a few (5-10) workbooks of any one type to run concurrently, so when more than 5-10 are all scheduled at once, some will need to wait in line for other workbooks to finish before they can begin processing. This issue can be mitigated by scheduling a company's workbooks at staggered times throughout the day or hour, rather than simultaneously.
> * Aside from the specific workbook type, workbooks will also wait in line if the company has **more than 15-20 of any type of workbook scheduled at once (across all different workbook types)**. This can be mitigated by staggering schedule times instead of having many run at the exact same time.
> * **Issues in downstream services** that the Scheduler relies on can also affect delivery of workbooks. For example, if you are independently using the APIs to run workbooks and fill up the API request queue, then your scheduled workbooks may deliver slowly while you compete for that resource.
> * **Report suite latency** (a delay in data collection) can also delay some scheduled workbooks.

## Schedule a workbook

1. Generate and save a workbook.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   The [!UICONTROL Scheduled Reports] tab summarizes all the tasks you have created, as well as the number of remaining tasks.
1. On the **[!UICONTROL Scheduled Reports]** tab, click **[!UICONTROL New]**. The Basic Scheduling Wizard shows the options used to define the scheduled report.

   ![Screenshot showing the Basic Scheduling Wizard.](assets/simple-schedule-wizard.png)

1. In the [!UICONTROL Basic Scheduling Wizard], configure the following options:

| Field | Description |
|--- |--- |
|Select Report|The name of the workbook. For new scheduled reports, this field is populated with the active workbook name.|
|Select|Displays the  Select Report page. You can select a report from the server (where all your previously scheduled workbooks are stored), or from your local machine. If you select a workbook from the local drive in  .xls format, the system converts the file to  .xlsx. As part of that conversion, the file is opened in Excel and made active. If the selected workbook for the scheduled report has the same filename as the workbook currently open in Excel, the system selects the local file instead of the previously uploaded file. If you select a report from the scheduling repository, a copy of the workbook is created on the server, with its filename updated with 1. The newly created scheduled report uses the copied workbook.|
|Customize|Lets you customize the date format.|
|To|Displays your Outlook Address Book, if applicable.|
|Send to: Email|The email recipient of the workbook.|
|Send to: Publishing List|Displays a list of available distribution lists for this company.|
|Power BI|See [Publish Workbook to Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md) for more information.|
|Subject|A user-defined description.|
|Scheduling|Lets you specify when to send the workbook. (Immediately, hourly, daily, weekly, monthly, and yearly.)| 

## Advanced Delivery Options

1. Click **[!UICONTROL Advanced Delivery Options]** to configure file and publishing options:

| Field | Description |
|--- |--- |
|**Scheduling tab**||
|Delivery Time|Lets you schedule the workbook immediately or for a later time. The time of day is relative to the time zone specified on your computer.|
|Recurrence Pattern|Sends the workbook based on your selections.|
|Range of Recurrence|Lets you specify when to start and stop receiving the workbook.   Note:  Scheduling a workbook on the first day of any current period (week, month, quarter, or year) returns data only for the first day.|
|**File Options tab**||
|File Format|Lets you select a delivery format of Excel 2007 ( .xlsx) or 2003 ( .xls),  .pdf, .csv, .mht, .txt, and .xml.|
|File Destination|Specifies Email or FTP. The options on the page change depending on your selection. For FTP, you must ensure that the host is available externally.|
|File Contents Language|Specifies the language you want to use for the cover letter. You can select Chinese (Simplified or Traditional), German, French, Japanese, Korean, Brazilian Portuguese, or Spanish.|
|**Publishing Options tab**||
|Publishing to Power BI|<ul><li>Publish Workbook to Power BI</li><li>Publish All Report Builder Requests as Power BI Datasets</li><li>Publish All Formatted Tables as Power BI Datasets</li></ul>|
|Label this Power BI Report as|Labeling details|

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   Report Builder displays the scheduled workbook in the [Scheduled Task Manager](/help/analyze/report-builder/r-arb-scheduled-reports.md).
