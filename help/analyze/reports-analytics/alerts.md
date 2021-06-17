---
description: Use alerts in Reports & Analytics.
subtopic: Alerts
title: Alerts
uuid: e1333a9b-eba0-45b7-b7e6-46e06190db64
feature: Alerts
role: Business Practitioner, Administrator
exl-id: f0a23afb-6c21-41e6-9033-9d3421bb1f4b
---
# Alerts

## Alerts {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

As the new alert system for all of Adobe Analytics, Intelligent Alerts let you create and manage alerts, complete with alert preview and rule contribution. You can

* Build alerts based on anomalies (90%, 95%, or 99% thresholds; % change; above/below).
* Preview how often an alert will trigger.
* Send alerts by e-mail or SMS with links to auto-generated Analysis Workspace projects.
* Create "stacked" alerts that capture multiple metrics in a single alert.

You can access this new Alerts system from **[!UICONTROL More]** > **[!UICONTROL Alerts]** in any report in Reports & Analytics.

For more information, go to the Analysis Workspace documentation on [Intelligent Alerts](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html).

## Add an Alert {#task_51187E8BF19544DDA9EF2057E6F11D35}

Steps that describe how to add an alert in Adobe Analytics.

<!-- 

t_add_an_alert.xml

 -->

Navigate to the new Alert Builder in the **[!UICONTROL Analytics]** > **[!UICONTROL Components]** menu. However, you can still access it from within reports in Reports & Analytics: 

1. In Reports & Analytics, open the report where you want to set an alert.
1. Click **[!UICONTROL More]** > **[!UICONTROL Add Alert]**.
1. This will take you to the [new Alert Builder](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/alert-builder.html).

## View or Edit Existing Alerts {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

Task Context 

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Alerts]**. This takes you to the new [Alert Manager](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/alert-manager.html).

## Legacy Alerts Migration {#concept_7E8179F5EF6E4913B0CE5CF4FF186911}

Several features of existing Analytics alerts will not be included in the new Alert Manager, which will be released (as part of Analysis Workspace) in the Fall of 2016. The following table lists the deprecated alert features and some alert features that will be migrated to the new Alert Manager in a different form.

<!-- 

deprecated_alerts.xml

 -->

<table id="table_9307013B16AC4AC7BFC6F4C440FCFDE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Legacy Alerts Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Deprecated or migrated? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Totals (All Items) </p> </td> 
   <td colname="col2"> <p>Create alerts on all items of a dimension report. </p> </td> 
   <td colname="col3"> <p>In some cases, whether you create an alert on all items of a dimension report or whether you set up the alert on just the aggregated metric by itself (not applied to a dimension), the same result occurs. For example, let's say you create a monthly All Items alert on the "Revenue" metric. You would get the same result from just running the Revenue report and setting up a monthly alert on it. </p> <p>In this situation, the legacy Totals (All Items) alert will no longer be available and will be migrated to the latter, simpler version. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Top 1000 Items </p> <p> </p> </td> 
   <td colname="col2"> <p>Create alerts for the top 1000 items in a report. </p> </td> 
   <td colname="col3"> <p>No longer available in the new Alert Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Time-based Unique Visitors Alerts (Daily, Weekly, Monthly, etc. Unique Visitors) </p> <p> </p> </td> 
   <td colname="col2"> <p>Create alerts for hourly, daily, weekly, and monthly unique visitors reports. </p> </td> 
   <td colname="col3"> <p>In the new Alert Manager, certain time-based Unique Visitor alerts will no longer be supported. For example, where you could previously set a weekly alert for Daily Unique Visitors, you will be able to set a daily, weekly, etc. alert on the Unique Visitors metric going forth. (Analysis Workspace supports a Unique Visitors metric, but not Daily/Weekly/Monthly/etc. Unique Visitors metrics.) </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Search </p> </td> 
   <td colname="col2"> <p>Create alerts for a dimension report with a search applied. Only applies to "Totals" ("All Items") or "Top 1000 Items". </p> <p> </p> </td> 
   <td colname="col3"> <p>No longer available in the new Alert Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reports specific to Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p>Create alerts for several reports that exist in Reports &amp; Analytics and do not correspond to an Analysis Workspace report, such as 
     <ul id="ul_9A690970A5AE4ED39E664DF23EF3164F"> 
      <li id="li_E2F44EDBA1D945CEBAC4802ED714E7A1">JavaScript </li> 
      <li id="li_B847C6A988854F76824F099681705EC9">Path Length </li> 
      <li id="li_4AF656460BC748E8802FAF258D01842F">Bots </li> 
      <li id="li_A300D2803B244774839BEC23D3EB533A">Timezones </li> 
      <li id="li_7A0B4CF92F4D47238B7B329EEC213322">Top Level Domains </li> 
     </ul> </p> <p> </p> </td> 
   <td colname="col3"> <p>No longer available in the new Alert Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alerts with an ASI slot as the report suite </p> </td> 
   <td colname="col2"> <p>You can no longer create or edit ASI slots and they are not available for use in Analysis Workspace. Hence, they are not supported by the new alerts. </p> <p> </p> </td> 
   <td colname="col3"> <p>Not available in the new Alert Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Monthly alerts for custom calendar report suites </p> </td> 
   <td colname="col2"> <p>This only affects customers with alerts set up for report suites that have <a href="https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/date-ranges/custom-calendar.html"  > custom month start dates </a> (National Retail Federation/NRF and Custom Calendar types). </p> <p>It does not affect alerts on Gregorian or Modified Gregorian calendar report suites. Previously these alerts were sent on the first day of the Gregorian month (e.g. January 1st, February 1st etc). This will not work with the new Anomaly Detection feature of alerts, which takes previous months' data into account when detecting anomalies. In the future, we will add support to our scheduling system for custom calendars so that both Alerts and Scheduled Projects can be scheduled to send on the first day of the custom calendar month instead of just the first day of the Gregorian month. </p> <p> </p> </td> 
   <td colname="col3"> <p>Not yet available in the new Alert Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alerts that haven't run since September 2015. </p> </td> 
   <td colname="col2"> <p>There are several reasons why alerts would not have run since September 2015, including: </p> 
    <ul id="ul_15812938A2454537AF6ADDB039DE16BC"> 
     <li id="li_D079A819CEE04F609AF18C09EEE83F0D">You clicked "Disable" on the alert in the Alert Manager. </li> 
     <li id="li_E23D01FA0B1341AD8BC1DDD16FB1366F">The alert is running into errors and never completes successfully. </li> 
    </ul> <p> </p> </td> 
   <td colname="col3"> These alerts will not be migrated to the new system. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alerts that were marked as "disabled" </td> 
   <td colname="col2"> There is currently no way to disable/re-enable alerts in the new user interface, though there are plans to add this functionality. <p> </p> </td> 
   <td colname="col3"> These alerts will not be migrated to the new system. </td> 
  </tr> 
 </tbody> 
</table>
