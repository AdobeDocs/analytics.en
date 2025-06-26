---
description: Send an Analysis Workspace project using email or schedule it for delivery.
keywords: Analysis Workspace
title: Schedule projects
feature: Curate and Share
role: User, Admin
exl-id: 2d6854f7-8954-4d55-b2be-25981cfb348b
---
# Send files to others

You can send Adobe Analytics reports as files to selected users by email. You can send files ad hoc, or you can configure files to be sent on a schedule. Files can be sent in CSV or PDF format.

Any tags applied to the project are automatically applied to the export.

Other methods of exporting Adobe Analytics data are also available, as described in [Export overview](/help/export/home.md).

![Send file](assets/send-file.png)

## Send file

To send a file to recipients by email:

1. Select **[!UICONTROL Share] > [!UICONTROL Send file]**.
1. Specify the file type:
   * [!UICONTROL **CSV**]: Choose this option if you want plain-text data.
   * [!UICONTROL **PDF**]: Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.
1. (Optional) Use **[!UICONTROL Description]** to add a description to include in the email. 
1. Add recipients or groups. You can also enter email addresses. 
1. (Optional) Select **[!UICONTROL Show scheduling options]** to [schedule a file export](#schedule-file-export).
1. Click **[!UICONTROL Send Now]**. Select **[!UICONTROL Cancel]** to cancel.


## Schedule file export {#schedule}

To send a file on a schedule to recipients by email

1. Select **[!UICONTROL Share] > [!UICONTROL Schedule file export]**.
1. Specify the file type:
   * [!UICONTROL **CSV**]: Choose this option if you want plain-text data.
   * [!UICONTROL **PDF**]: Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.
1. (Optional) Use **[!UICONTROL Description]** to add a description to include in the email. 
1. Add recipients or groups. You can also enter email addresses. 
1. (Only for Healthcare Shield customers) Provide a password to [password-protect a scheduled report](#password-protect-a-new-scheduled-project).
1. Ensure **[!UICONTROL Show scheduling options]**  is selected.
1. Select a **[!UICONTROL Frequency]**. You can select between:

   | Frequency | Options |
   |---|---|
   | **[!UICONTROL Send hourly]** | Enter a value for **[!UICONTROL Send every number of hours]**. |
   | **[!UICONTROL Send daily]** | Select a **[!UICONTROL Daily frequency]**: **[!UICONTROL Send every day]**, **[!UICONTROL Send every weekday]**, or **[!UICONTROL Custom frequency]**.<br/>If you select **[!UICONTROL Custom frequency]**, enter a value for **[!UICONTROL Send every number of days]**. |
   | **[!UICONTROL Send weekly]** | Enter a value for **[!UICONTROL Send every number of weeks]**. And select a **[!UICONTROL Day of week]**. |
   | **[!UICONTROL Send monthly by day of the week]** | Select a **[!UICONTROL Day of week]** and a **[!UICONTROL Week of month]**. |
   | **[!UICONTROL Send monthly by day of the month]** | Select a value from **[!UICONTROL Send on this day of the month]**. |
   | **[!UICONTROL Send yearly by day of the month]** | Select a **[!UICONTROL Day of week]**, select a **[!UICONTROL Week of month]**, and select a **[!UICONTROL Monthly of year]**. |
   | **[!UICONTROL Send yearly by specific date]** | Select a **[!UICONTROL Month of year]** and select a value from **[!UICONTROL Send on this day of the month]**. |

1. Enter a start date in **[!UICONTROL Starting on]**. Alternatively, select ![Calendar](/help/assets/icons/Calendar.svg) to pick a start date from the calendar.
   
1. Enter an end date in **[!UICONTROL Ending on]**. Alternatively, select ![Calendar](/help/assets/icons/Calendar.svg) to pick an end date from the calendar.
1. Select **[!UICONTROL Send on schedule]**. Select **[!UICONTROL Cancel]** to cancel.


## Scheduled Projects manager {#manager}

Scheduled Analysis Workspace projects can be managed from the main interface, using **[!UICONTROL Components]** > **[!UICONTROL Scheduled Projects]**. For more information, see [Scheduled projects](/help/components/scheduled-projects-manager.md).

<!--
# Schedule projects

From the Workspace **Share menu**, you can send Analysis Workspace projects using email to selected recipients. Files can be sent in CSV or PDF format. After you share scheduled projects, you can edit the schedule settings to modify the frequency, receipient list, or file type using the Scheduled Projects manager.

## Send file now

To send a file immediately to recipients via email:

1. Click **[!UICONTROL Share] > [!UICONTROL Export file]**.
1. Specify the file type:
   * [!UICONTROL **CSV**]: Choose this option if you want plain-text data.
   * [!UICONTROL **PDF**]: Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.
1. (Optional) Add a description to include in the email to explain the file being received. 
1. Add recipients or groups. Email addresses can also be entered. 
1. Click **[!UICONTROL Send Now]**.
1. (Optional) Click **[!UICONTROL Show scheduling options]** to specify a delivery schedule.

![Send file now](assets/send-file-now.png)

## Send file on schedule

To send a file on a recurring schedule to recipients via email:

1. Click **[!UICONTROL Share] > [!UICONTROL Schedule file export]**.
1. Specify the file type (CSV or PDF).
1. (Optional) Add a description that will be included in the email to explain the file being received. 
1. Add recipients or groups. Email addresses can also be entered. 
1. Specify the range the schedule should be delivered over by modifying Starting on and Ending on inputs. The end date must be within a year from the day the schedule is created or modified.
1. Specify the delivery frequency. Each frequency allows for different customizations. 
1. Click **[!UICONTROL Send on schedule]**.

![](assets/send-on-schedule.png)

## Manage scheduled projects

When you manage scheduled projects, you can edit and delete recurring project schedules:

*  Change the file type (.csv or PDF)
*  Update the project description
*  Add or remove recipients
*  Change the frequency


Scheduled Analysis Workspace projects can be managed under **Analytics > Components > Scheduled Projects**.

For more information, see [Scheduled projects](/help/components/scheduled-projects-manager.md)
-->
