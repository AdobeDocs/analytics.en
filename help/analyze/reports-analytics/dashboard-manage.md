---
description: Use the Dashboard Manager to copy, share, archive, and schedule dashboards for delivery.
seo-description: Use the Dashboard Manager to copy, share, archive, and schedule dashboards for delivery.
seo-title: Dashboard Manager
solution: Analytics
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

## Dashboard Manager {#concept_E1301CF138EB477794B00F693B4FCA0F}

Use the Dashboard Manager to copy, share, archive, and schedule dashboards for delivery. 

Click **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**. 

<p class="head"> <b>Dashboard Manager Descriptions</b> </p>

<table id="table_EEE9323474DB432EB40EE33E1A85EE50"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dashboard Player </td> 
   <td colname="col2"> <p>SiteCatalyst 14 servers will no longer respond to Dashboard Player data requests. Any dashboards currently being displayed in Dashboard Player can be accessed in the standard Reports &amp; Analytics interface or recreated as a Real-Time Dashboard. Real-Time dashboards are specifically designed for continual display and include a full-screen mode to allow you to display on TVs or other large screen devices. </p> <p>User action required: You need to discontinue use of Dashboard Player. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Shared </td> 
   <td colname="col2"> <p>Shows whether the dashboard is shared. </p> <p>See <a href="../../analyze/reports-analytics/dashboard-manage.md#task_2776BDE3FBC64E66B78DB6D6A53AAF49" format="dita" scope="local"> Share a dashboard </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scheduled </td> 
   <td colname="col2"> <p>Lets you schedule the dashboard for delivery. </p> <p>See <a href="../../analyze/reports-analytics/dashboard-manage.md#task_639361A35E044B2DB9D50FCABEC776FF" format="dita" scope="local"> Schedule a dashboard for delivery </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> View Archive </td> 
   <td colname="col2"> <p>Lets you view the dashboard archive. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Push to Users </td> 
   <td colname="col2"> <p>Lets you share a dashboard. </p> <p>See <a href="../../analyze/reports-analytics/dashboard-manage.md#task_2776BDE3FBC64E66B78DB6D6A53AAF49" format="dita" scope="local"> Share a dashboard </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Manage </td> 
   <td colname="col2"> <p>Lets you edit, copy, and delete a dashboard. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Manage shared dashboards {#task_06BA6636471B4252A8A4DA2E99B9DFCF}

Steps that describe how use the shared dashboard management options.

<!-- 

t_dashboard_copy.xml

 -->

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.
1. Under [!UICONTROL Shared Dashboards], locate the shared dashboard (or legacy dashboard) you want to manage and choose one or more of the following options:

<table id="choicetable_857E0E816D63404683D4E24DC8D7FC69"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> Option </th> 
  <th class="chdeschd"> Description </th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>View Archive</strong></td> 
  <td class="chdesc stentry"> Lets you view the report archive for the shared dashboard, if an archive exists. </td> 
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

## Migrate a legacy dashboard {#task_64E4A29DB99644FA82EB3372243F1417}

Existing legacy dashboards will continue to be run and you can still edit, download, and schedule them; however, you can no longer create new legacy dashboards. You are strongly encouraged to upgrade existing legacy dashboards to the newer dashboard format.

<!-- 

t_dashboard_migrate_legacy.xml

 -->

>[!NOTE]
>
>Moving forward, consider using [Analysis Workspace projects](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) and their ability to be downloaded and scheduled.

When you copy the legacy dashboard, the system opens the legacy dashboard for edit, where you can add legacy content or new content. When you copy a legacy dashboard, the original is preserved in the list of legacy dashboards.

>[!NOTE]
>
>Adding legacy content to a dashboard creates a dashboard based on the latest dashboard functionality. However, the legacy reportlet might contain data that is based on the previous data platform.

**To migrate a version 14.x legacy dashboard** 

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. In the [!UICONTROL Manage] column, under [!UICONTROL Legacy Dashboards], click **[!UICONTROL Copy to New Dashboard]**.

   The copied dashboard opens in the dashboard layout editor.

   See [Editing Dashboard and Reportlet Data](../../analyze/reports-analytics/dashboard.md#task_B460CCD70D9F40FCAC6BBC1C044CC460). 

## Share a dashboard {#task_2776BDE3FBC64E66B78DB6D6A53AAF49}

Steps that describe how an administrator can share (or push) a dashboard to multiple users. When you push dashboards to users, the dashboards become available in user's [!UICONTROL Shared Dashboards] menu.

<!-- 

t_dashboard_share.xml

 -->

1. In the [!UICONTROL Dashboard Manager], locate the dashboard, then enable **[!UICONTROL Shared]**.
1. Click **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. On the [!UICONTROL Push Dashboard] page, select the target users or click **[!UICONTROL Check All]**.
1. Click **[!UICONTROL Save]**.

If shared users of your dashboard cannot see changes you made in the dashboard, check your Dashboard Manager to see if the users have chosen the **[!UICONTROL Copy Me]** option. If they did, they cannot see the updates/changes made by you. To see all the changes/updates, shared users need to select the **[!UICONTROL On Menu]** option in the Dashboard Manager. 

## Schedule a dashboard for delivery {#task_639361A35E044B2DB9D50FCABEC776FF}

In the [!UICONTROL Dashboard Manager], you can see whether a dashboard is scheduled for delivery, and edit the schedule. The dashboard delivery options are identical to the report delivery options. 


<!-- 

t_dashboard_delivery.xml

 -->

1. Open a dashboard.
1. Click **[!UICONTROL More]** > **[!UICONTROL Send]**.

   See [Schedule and Distribution](../../analyze/reports-analytics/scheduling.md#concept_4EA333DFC7FD4E9CA086385A3DA10BE9) for more information. 

## Archive a dashboard {#task_3B6AB949F0EC4063A08F80F254992117}

Steps that describe how to archive any sent dashboard as a PDF file. The system stores the archived file for two years, or until you reach a maximum limit of 4 GB of archived reports, whichever comes first. 

<!-- 

t_dashboard_archive.xml

 -->

1. Open a dashboard.
1. Click **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. In the [!UICONTROL Email Report] group, enable **[!UICONTROL Archive]**.
1. Specify delivery options, then click **[!UICONTROL Send]**.

   You can view archived dashboards in the Dashboard Manager. Alternatively, open a dashboard and click **[!UICONTROL More]** > **[!UICONTROL View Archive]**. 
