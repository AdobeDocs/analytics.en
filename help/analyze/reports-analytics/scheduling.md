---
description: Information about scheduling, downloading and distributing reports.
subtopic: Schedule
title: Report schedule and distribution
uuid: 1230b0f3-e026-4b83-b231-14d6f75a3836
feature: Reports & Analytics Basics,Reports and analytics
role: Business Practitioner, Administrator
exl-id: ec59d365-f294-41da-ae36-3b4ebe64ab23
---
# Report schedule and distribution

Information about scheduling, downloading and distributing reports.

When you schedule a report for delivery in an Adobe Analytics application, you can use the Scheduling and Distribution tools to view what files have been automatically sent and modify or terminate the deliveries.

Due to differences in processing mechanisms and platforms, the various types of downloadable and scheduled reports available in Adobe Analytics have different limitations regarding the maximum number of rows they can process in a single request. Here are the limits of each:

* Word, CSV, Excel, HTML and PDF: The same number of rows visible in the report. By default this limit is 50 rows but can increase up to 200. Breakdown reports have a hard limit of 50 rows.
* Data Extracts: 50,000 rows 
* Data Warehouse: Unlimited

These limitations are for individual scheduled and downloaded reports; dashboards are limited to the amount of space available within a reportlet.

>[!NOTE]
>
>The "Delivery Time"/"Time of Day" entered by the user specifies the time that the report should begin processing, not the time that it will actually be delivered. The actual time that the report will be delivered is based primarily on how long it takes to process (complex and large reports take longer to process than simpler reports). For example, if a report takes 15 minutes to process, then the actual delivery time will be at least 15 minutes past the originally specified "Delivery Time"/"Time of Day".
>In addition, there are a number of other factors that can further increase the delay before the report is actually delivered:
>
> * **Running many different schedules of the same type at the same time** (e.g., many Dashboards, etc.) can overload the system. The Scheduling system only allows a few (5-10) reports of any one type to run concurrently, so when more than 5-10 are all scheduled at once, some will need to wait in line for other reports to finish before they can begin processing. This issue can be mitigated by scheduling a company's reports at staggered times throughout the day or hour, rather than simultaneously.
> * Aside from the specific report type (Dashboards, etc.), reports will also wait in line if the company has **more than 15-20 of any type of report scheduled at once (across all different report types)**. This can be mitigated by staggering schedule times instead of having many run at the exact same time.
> * **Issues in downstream services** that the Scheduler relies on can also affect delivery of reports. For example, if you are independently using the APIs to run reports and fill up the API request queue, then your scheduled reports may deliver slowly while you compete for that resource.
> * **Report suite latency** (a delay in data collection) can also delay some scheduled reports.


## Send a report {#task_27642CD33D484FD0BF59EBD159EEF52C}

Steps that describe how to download and email reports in a variety of formats, and schedule a report for delivery.

1. Run a report, then click **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. Specify delivery options:

   | Option  | Description  |
   |--- |--- |
   |Format|Select PDF or HTML.|
   |Send To|Provide an email address to receive the report.|
   |Subject|Subject of the email.|
   |Scheduling|Select to send the report immediately or at a different interval.|

1. Click **[!UICONTROL Advanced Delivery Options]** to specify a delivery schedule.

| Option | Description |
|--- |--- |
|Report File Name|Specifies the name of the report. The default format is `<report name> for <suite> - <report date range>`. To specify a custom name, select [!UICONTROL Custom].|
|Report Format|Lets you specify PDF, CSV, Excel, HTML, Word, or Mobile formats for delivery. If you select CSV, you can also specify the encoding for CSV:<ul><li>Shift-JIS: Japanese character encoding.</li><li>EUC-JP: Extended Unix Code, primarily for Japanese, Korean, and Simplified Chinese.</li></ul>|
|Report Contents|<ul><li>Number of rows in the table: Specifies the number of rows you want visible in the table of the report you are sending.</li><li>Language for header and footer: Specifies the language of the header and footer.</li><li>Comments: Specifies the text that appears at the beginning of the report.</li></ul>|
|Send Digital Signature File|When you request a report, such as a bookmarked report or Data Warehouse requests, you can request a data signature. Adobe's digital signature doesn't restrict who has access to the data, but the purpose of the Digital Signature File (.sig) is to verify the validity of the delivered report file. Using the digital signature, report recipients can verify that the file came from Adobe and has not been altered.|
|Report Destination|<ul><li>Email: Lets you configure email address settings, the subject line, and notes.</li><li>FTP: Lets you configure FTP settings, including the Host, Port, Directory, Username, and Password.</li></ul>|

1. Click **[!UICONTROL Scheduling Options]**.

| Option | Description |
|--- |--- |
|Send Report Now|Sends the report immediately.|
|Schedule for Later|Displays options to specify a time frame and delivery options.|
|Report Time Frame|**Fixed**: Prevents the date from advancing as time passes. **Rolling**: Allows the date to advance as time passes. Some considerations:<ul><li>If you select Rolling for both the start and end dates, and you select a daily report for the previous day, you receive an email each day with a report for the previous day.</li><li>If you select Fixed for the starting day, and rolling for the end day, you receive on the first day a report for the previous day. The second day you receive a report for the previous two days, and on the third day you receive a report for the previous three days, and so on.</li><li>If you select Fixed for both the beginning and ending dates, each day you receive an identical report for the days that you specified.</li><li>You cannot select a rolling start date and a fixed finish date.</li></ul>|
|Delivery Frequency|<ul><li>**Hourly**: Delivers the email every hour, every other hour, or any other interval of hours.</li><li>**Daily**: Sends the email every day, every other day, every third day, or any other interval of days. You can also have it sent every weekday.</li><li>**Weekly**: Sends the email every week, other week, every third week, or any other interval of weeks. You can also specify which day of the week it is sent.</li><li>**Monthly**: Specifies the interval in numbers of months, and you can also select the day of the month on which it is sent, or the day of the week in a specific week of the month.</li><li>**Yearly**: Specifies the day of the year on which the report is sent, or you can send on a specific day of the week in any week of the year.</li><li>**Time of Day**: Applies to the time zone attached to the selected report suite.</li></ul>|
|End Delivery Options|<ul><li>**Never end**: Specifies no end.</li><li>**End after `value` occurrences**: Specifies the number of occurrences before ending delivery.</li><li>**End on**: Lets you specify a specific date. If you want to process the data on the same date as the report data, the report contains only data that has been put in the database at the time the report is sent. Because complete processing for a day can take up to 24 hours, complete data might not be available at the time the report is sent. For complete data, always set the processing time for 24 hours after the end of the reporting period.</li></ul>|

## Print a report {#task_0F7CF6D6ED54462CAE4A793E271AF7E5}

Steps that describe how to print a report.

1. Run a report.
1. Click **[!UICONTROL More]** > **[!UICONTROL Print]**.  ![](assets/print.png)

## Download a report using basic options {#task_43660107A1C9485D92981CD75B562577}

Download detailed information about a specific report in PDF, CSV, Excel, or Raw Data Export formats.

1. In  **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** , select a report to view.
1. Click **[!UICONTROL Download]**.

   ![](assets/download_basic.png)

1. Select the desired format for the report:

    * **[!UICONTROL PDF]**: Specifies that the report will be downloaded in Adobe PDF, which lets you share the report with others, regardless of which computer system the recipient is running.
    * **[!UICONTROL CSV]**: Specifies that the report will be downloaded in [!DNL .csv] (comma-separated values format).
    * **[!UICONTROL Excel]**: Specifies that the report will be downloaded in Microsoft Excel format, which lets you share the report with other who can open it in a spreadsheet program.
    * **[!UICONTROL Word]**: Specifies that the report will be downloaded in Microsoft Word format.

   >[!NOTE]
   >
   >If you use one of the raw export formats to download a report and the page name is blank, Adobe Analytics likely has not had enough time to process the data. Download the report at a later time.

## Manage scheduled reports {#task_C17677C543454FF2B06D10EA5652DFBC}

Information about managing scheduled reports.

In the [!UICONTROL Schedule Reports Manager], you can edit and delete recurring report deliveries. You can create delivery schedules that send your reports via email or FTP to a specified address. You can configure these schedules to automatically send the reports at specified intervals for a duration of time or indefinitely, or stop the delivery of a recurring report.

The [!UICONTROL Schedule Report Manager] shows the items that a specific user has created. If the user account is disabled in the application, all scheduled deliveries stop.

1. To access the manager, click **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL All components]** > **[!UICONTROL Scheduled reports]**.

## Share a report link {#task_9711DDE9E140451B8C914EC5513E21EC}

Steps that describe how to share a report by generating a report link (URL) to send to another user.

When the recipient clicks the link, the system requests login credentials (company name, user name, and password). After logging in, the recipient is shown the report generated by the original user. Standard permission restrictions apply.

**To share a report link** 

1. Run a report.
1. Click **[!UICONTROL More]** > **[!UICONTROL Link to This Report]**.

## Unsubscribe from scheduled reports {#concept_6B48360F935740B6851BA85D32DEF637}

You can unsubscribe from scheduled reports. You will no longer receive the report even if your user name is re-added to the scheduled report.

>[!IMPORTANT]
>
>In order for you to again receive the report, a new schedule needs to be created.

To unsubscribe from a scheduled report:

1. Bring up the email with the link to the report from which you want to unsubscribe.

   ![](assets/unsubscribe-email.png)

1. Click the **[!UICONTROL click here]** link next to **[!UICONTROL To cancel automatic delivery of this report]**.

1. Confirm that you want to cancel the report delivery.

   >[!NOTE]
   >
   >This workflow is the same whether you are the report scheduler or the report recipient.

Unsubscribing from a report does not cancel the scheduled report.

To cancel a scheduled report, navigate to the Schedule Manager and click on the red X next to the report name. [More...](/help/analyze/reports-analytics/scheduling.md#task_C17677C543454FF2B06D10EA5652DFBC)
