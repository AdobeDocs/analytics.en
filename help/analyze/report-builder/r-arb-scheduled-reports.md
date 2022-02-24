---
description: Field descriptions for the Scheduled Task Manager.
title: Scheduled Task Manager
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
---
# Scheduled Task Manager

The [!UICONTROL Scheduled Task Manager] lets you see a list of existing scheduled reports, along with their recipients, schedule details, and file formats. It also lets you reactivate scheduled workbooks that failed to run.

## Pausing older scheduled tasks 

**Effective April 15, 2022**, Adobe intends to pause all scheduled Report Builder tasks that were created more than two years ago. Specifically, this pause applies to **any tasks created before January 31, 2020**. No tasks, workbooks or data will be deleted. Tasks that are older than two years will be paused, and no additional scheduled tasks will be sent.
 
Any tasks that you wish to resume sending can be reactivated. Log in to Report Builder and launch the [!UICONTROL Scheduled Task Manager]. Click **[!UICONTROL Reactivate]** for the scheduled task you would like to resume sending. Any task that gets reactivated will have a default expiration of 18 months - unless a shorter expiration date is chosen.
 
In addition, any task with a creation date of less than two years, and with no current expiration date (or with an expiration date longer than two years) will have a default 18-month expiration date applied to it. The new expiration date will be October 15, 2023. You can edit this expiration date to be less than 18 months, but not greater. At the time of expiration, the task will be paused. However, you can reactivate the task with a new 18-month expiration date. No tasks, workbooks or data will be deleted.
 
The purpose of this pause is to effectively manage and maintain our scheduled tasks database to ensure optimal performance and delivery for needed tasks and workbooks. This will serve as our new governance policy moving forward. After April 15, 2022, all tasks will have a maximum expiration date of 18 months. After 18 months, expired tasks will be paused and can be reactivated as needed. 

## Configure scheduled tasks

| Field | Description |
| --- | --- |
| **[!UICONTROL Scheduled Reports tab]** | |
| [!UICONTROL Report Name] | Indicates the name of the scheduled task. |
| [!UICONTROL Email/FTP] | The email or FTP address of the recipient. **Note:** If email is selected, reports larger than 1 MB are automatically attached to the email as a .zip file. This feature helps keep attachment file size small and cannot be disabled. |
| [!UICONTROL Publishing Options] | This column will list Power BI if one of the [Power BI publishing options](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/publish-powerbi/power-bi.html) is selected. |
| [!UICONTROL Schedule] | The type of delivery scheduled. |
| [!UICONTROL File Format] | The delivery format of the report, such as Excel, PDF, HTML, and so on. |
| [!UICONTROL Reactivate] | When a scheduled workbook fails to run, Report Builder attempts to run the workbook two more times every fifteen minutes. After three failed attempts, Report Builder deactivates the schedule and displays the  Reactivate button. When you reactivate a workbook, the scheduled delivery restarts from the time it became deactivated.  For example, if a scheduled workbook was deactivated 14 days ago, and you reactivate it today, it runs for every missing day and will be delivered 14 times. If you do not want the workbook delivered for the missing days, you can delete the scheduled workbook and then create a new scheduled workbook using the same scheduling parameters.   Note:  You should not reactivate a workbook unless you know the reason the system deactivated it. One troubleshooting solution is to download a deactivated workbook, and refresh it on the client side. If you see no errors, you should be able to reactivate it. |
| [!UICONTROL Last sent] | The date and time when the report was last sent. |
| **Recipient tab** | |
| [!UICONTROL Recipient email] | The email recipient of the report. |
| [!UICONTROL Reports] | The reports that were sent to each recipient. |
| **Reports History tab** | |
| [!UICONTROL File Name] | Indicates the name of the scheduled task.|
| [!UICONTROL Date] | The date and time when the report was last sent. |
| [!UICONTROL Status] | The status indicates whether the report was Sent or Not Sent. |
| [!UICONTROL Email/FTP] | The email or FTP address of the recipient of the report. |
| [!UICONTROL File Format] | The delivery format of the report, such as Excel, PDF, HTML, and so on. |
