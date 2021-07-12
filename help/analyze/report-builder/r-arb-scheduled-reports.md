---
description: Field descriptions for the Scheduled Task Manager.
title: Scheduled Task Manager
uuid: dec259f0-2a04-4c94-abbc-5008cf2f1cb8
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
---
# Scheduled Task Manager

The Scheduled Task Manager lets you see a list of existing scheduled reports, along with their recipients, schedule details, and file formats. It also lets you reactivate scheduled workbooks that failed to run.

| Field | Description |
| --- | --- |
| **Scheduled Reports tab** | |
| Report Name | Indicates the name of the scheduled task. |
| Email/FTP | The email or FTP address of the recipient. **Note:** If email is selected, reports larger than 1 MB are automatically attached to the email as a .zip file. This feature helps keep attachment file size small and cannot be disabled. |
| Publishing Options | This column will list Power BI if one of the [Power BI publishing options](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/publish-powerbi/power-bi.html) is selected. |
| Schedule | The type of delivery scheduled. |
| File Format | The delivery format of the report, such as Excel, PDF, HTML, and so on. |
| Reactivate | When a scheduled workbook fails to run, Report Builder attempts to run the workbook two more times every fifteen minutes. After three failed attempts, Report Builder deactivates the schedule and displays the  Reactivate button. When you reactivate a workbook, the scheduled delivery restarts from the time it became deactivated.  For example, if a scheduled workbook was deactivated 14 days ago, and you reactivate it today, it runs for every missing day and will be delivered 14 times. If you do not want the workbook delivered for the missing days, you can delete the scheduled workbook and then create a new scheduled workbook using the same scheduling parameters.   Note:  You should not reactivate a workbook unless you know the reason the system deactivated it. One troubleshooting solution is to download a deactivated workbook, and refresh it on the client side. If you see no errors, you should be able to reactivate it. |
| Last sent | The date and time when the report was last sent. |
| **Recipient tab** | |
| Recipient email | The email recipient of the report. |
| Reports | The report/s that were sent to each recipient. |
| **Reports History tab** | |
| File Name | Indicates the name of the scheduled task.|
| Date | The date and time when the report was last sent. |
| Status | The status indicates whether the report was Sent or Not Sent. |
| Email/FTP | The email or FTP address of the recipient of the report. |
| File Format | The delivery format of the report, such as Excel, PDF, HTML, and so on. |
