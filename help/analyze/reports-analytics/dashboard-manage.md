---
description: Use the Dashboard Manager to copy, share, archive, and schedule dashboards for delivery.
subtopic: Dashboards
title: Dashboard Manager
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
---

# Dashboard Manager

Use the Dashboard Manager to copy, share, archive, and schedule dashboards for delivery.

>[!IMPORTANT]
>
>Best practice when using the Dashboard Manager is to have no more than 300 dashboards for any single user. Also, please note that the manager loads all shared dashboards below, so be judicious with sharing dashboards.

## Dashboard Manager

Use the Dashboard Manager to copy, share, archive, and schedule dashboards for delivery.

Click **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.

| Element | Description |
|--- |--- |
|Shared|Shows whether the dashboard is shared.|
|Scheduled|Lets you schedule the dashboard for delivery.|
|View Archive|This functionality is no longer available.|
|Push to Users|Lets you share a dashboard.|
|Manage|Lets you edit, copy, and delete a dashboard.|

## Manage shared dashboards

Steps that describe how use the shared dashboard management options.

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.
1. Under [!UICONTROL Shared Dashboards], locate the shared dashboard (or legacy dashboard) you want to manage and choose one or more of the following options:

<table id="choicetable_857E0E816D63404683D4E24DC8D7FC69"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> Option </th> 
  <th class="chdeschd"> Description </th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>View Archive</strong></td> 
  <td class="chdesc stentry"> This functionality is no longer available. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Dashboard Player</strong></td> 
  <td class="chdesc stentry"> <p>SiteCatalyst 14 servers will no longer respond to Dashboard Player data requests. Any dashboards currently being displayed in Dashboard Player can be accessed in the standard Reports &amp; Analytics interface or recreated as a Real-Time Dashboard. Real-Time dashboards are specifically designed for continual display and include a full-screen mode to allow you to display on TVs or other large screen devices. </p> <p>User action required: You need to discontinue use of Dashboard Player. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Copy Me</strong></td> 
  <td class="chdesc stentry"> Adds a copy to your list of dashboards, using the same name as the original. However, you cannot see any updates/changes made by the dashboard's owner. Copying a legacy dashboard opens a blank dashboard, in which you can add legacy content. <p>Important:  If shared users of your dashboard cannot see changes you made in the dashboard, check your Dashboard Manager to see if the users have chosen the <span class="uicontrol"> Copy Me </span> option. If they did, they cannot see the updates/changes made by you. To see all the changes/updates, shared users need to select the <span class="uicontrol"> On Menu </span> option in the Dashboard Manager. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>On Menu</strong></td> 
  <td class="chdesc stentry"> Lets you see changes/updates made by the dashboard owner. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Unshare</strong></td> 
  <td class="chdesc stentry"> Removes the dashboard from your list of shared dashboards. </td> 
 </tr> 
</table>

## Migrate a legacy dashboard

Existing legacy dashboards will continue to be run and you can still edit, download, and schedule them; however, you can no longer create new legacy dashboards. You are strongly encouraged to upgrade existing legacy dashboards to the newer dashboard format.

> [!NOTE] Moving forward, consider using [Analysis Workspace projects](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) and their ability to be downloaded and scheduled.

When you copy the legacy dashboard, the system opens the legacy dashboard for edit, where you can add legacy content or new content. When you copy a legacy dashboard, the original is preserved in the list of legacy dashboards.

> [!NOTE] Adding legacy content to a dashboard creates a dashboard based on the latest dashboard functionality. However, the legacy reportlet might contain data that is based on the previous data platform.

**To migrate a version 14.x legacy dashboard** 

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. In the [!UICONTROL Manage] column, under [!UICONTROL Legacy Dashboards], click **[!UICONTROL Copy to New Dashboard]**.

   The copied dashboard opens in the dashboard layout editor.

   See [Editing Dashboard and Reportlet Data](/help/analyze/reports-analytics/dashboard.md).

## Share a dashboard

Steps that describe how an administrator can share (or push) a dashboard to multiple users. When you push dashboards to users, the dashboards become available in user's [!UICONTROL Shared Dashboards] menu.

1. In the [!UICONTROL Dashboard Manager], locate the dashboard, then enable **[!UICONTROL Shared]**.
1. Click **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. On the [!UICONTROL Push Dashboard] page, select the target users or click **[!UICONTROL Check All]**.
1. Click **[!UICONTROL Save]**.

If shared users of your dashboard cannot see changes you made in the dashboard, check your Dashboard Manager to see if the users have chosen the **[!UICONTROL Copy Me]** option. If they did, they cannot see the updates/changes made by you. To see all the changes/updates, shared users need to select the **[!UICONTROL On Menu]** option in the Dashboard Manager.

## Schedule a dashboard for delivery

In the [!UICONTROL Dashboard Manager], you can see whether a dashboard is scheduled for delivery, and edit the schedule. The dashboard delivery options are identical to the report delivery options.

1. Open a dashboard.
1. Click **[!UICONTROL More]** > **[!UICONTROL Send]**.

   See [Schedule and Distribution](/help/analyze/reports-analytics/scheduling.md) for more information.

## Archive a dashboard

> [!NOTE] This functionality will no longer be available in January, 2020.

Steps that describe how to archive any sent dashboard as a PDF file. The system stores the archived file for two years, or until you reach a maximum limit of 4 GB of archived reports, whichever comes first.

1. Open a dashboard.
1. Click **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. In the [!UICONTROL Email Report] group, enable **[!UICONTROL Archive]**.
1. Specify delivery options, then click **[!UICONTROL Send]**.

   You can view archived dashboards in the Dashboard Manager. Alternatively, open a dashboard and click **[!UICONTROL More]** > **[!UICONTROL View Archive]**.
