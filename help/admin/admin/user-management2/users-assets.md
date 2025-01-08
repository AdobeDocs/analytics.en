---
description: Manage Analytics users and their assets in the Adobe Admin Console.
title: Manage Analytics users and assets
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
---
# Manage legacy user accounts, assets, expirations

You can manage legacy user accounts, their migration status, the expiration data, the transfer of assets to other users, and more using **[!UICONTROL Admin] > [!UICONTROL All Admin] >  [!UICONTROL Analytics users & admin]**. 

The Users screen shows a list of current Adobe Analytics users, with the following columns:

| Column | Description |
|---|---|
| [!UICONTROL User ID] | The user id that the user uses to log in to Adobe Analytics.|
| [!UICONTROL Name] | The name of the user. |
| [!UICONTROL Migration status] | The status of the migration from a legacy user account to an Enterprise ID or Adobe ID.  The status can be Not initiated, Queued or Migrated. |
| [!UICONTROL Email] | The email of the user. |
| [!UICONTROL Legacy login] | The status of legacy login, which can be Enabled or Disabled. |
| [!UICONTROL Date created] | Timestamp when the user account was created in the Adobe Analytics. |
| [!UICONTROL Last Analytics access] | Timestamp of latest access of the user account to Adobe Analytics, |
| [!UICONTROL Expiration] | Date of expiration for the user account, or None if the user account is not expiring. | 

![Users](assets/users.png)

- To search for a specific user, use the ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) *Search by title* field.
- To filter the list on migration status, select ![Chevron](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Migration status]**. 
- To filter the list on legacy login status, select ![Chevron](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Legacy login]**.
- To change the display of columns, select ![Column settings](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) and select the columns from the popup.

You can apply various actions when selecting one or more users from the list:

|  Action  | Description  |
|---|---|
| ![Migrate](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Briefcase_18_N.svg) **[!UICONTROL Migrate]** | You can migrate one or more users to Enterprise IDs or Adobe IDs. |
| ![Calendar locked](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CalendarLocked_18_N.svg) **[!UICONTROL Set expiration]** | You can set an expiration date for using legacy Adobe Analytics login for the selected users.  Select the date to use a calendar popup to specify the date. Select **[!UICONTROL Done]** to confirm the expiration. |
| ![Transfer assets](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Switch_18_N.svg) **[!UICONTROL Transfer assets]** | This action is only available when selecting one user. If the user has assets that can be transferred, you can select the account items (like bookmarks, dashboards, and more). Select **[!UICONTROL Transfer]** to complete the transfer.<br/>![Transfers assets](assets/transfer-assets.png) |
| ![Delete accounts](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete accounts]** | A dialog is shown to confirm the deletion of the selected accounts. Select **[!UICONTROL OK]** to delete the accounts. Select **[!UICONTROL Cancel]** to cancel. |
| ![Export to CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL Export to CSV]** | This action immediately downloads a file containing a comma-separated value list of the selected users with their details (name, migration status, email, and more). |

