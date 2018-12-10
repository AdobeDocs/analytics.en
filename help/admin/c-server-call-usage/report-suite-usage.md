---
description: The Report Suite Usage tab provides server usage data for each report suite in all Login companies tied to your Billing company, for the current usage period.
seo-description: The Report Suite Usage tab provides server usage data for each report suite in all Login companies tied to your Billing company, for the current usage period.
seo-title: View report suite usage
title: View report suite usage
uuid: c609ed99-9acc-4023-905a-81a40dd07a79
index: y
internal: n
snippet: y
---

# View report suite usage

The Report Suite Usage tab provides server usage data for each report suite in all Login companies tied to your Billing company, for the current usage period.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Server Call Usage]** > **[!UICONTROL Report Suite Usage]**

>[!IMPORTANT]
>
>If a report suite is not [linked to an Experience Cloud Organization](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html), its usage data will not be reflected in this dashboard. Also, a billing ID could be tied to multiple Experience Cloud Orgs; there is not always a 1:1 relationship between an org and a billing ID.

The Report Suite Usage dashboard

* Shows the current usage period's server call usage (All Calls, Primary, Secondary, Mobile Primary, Mobile Secondary) for each report suite in your Experience Cloud organization. 
* Shows percentage of overall usage per server call category. 
* Is updated daily. 
* Is downloadable. 
* Lets you access the **[!UICONTROL Manage Alerts]** UI.

![](assets/report-suite-usage.png)

<table id="table_C2775A6364E140B6BE35E8DBBE384152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Column </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Report Suite Name </p> </td> 
   <td colname="col2"> <p>Friendly name of the report suite </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>All Calls (% of Total) </p> </td> 
   <td colname="col2"> <p>All server calls incurred in the current usage period. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Primary Calls (%) </p> </td> 
   <td colname="col2"> <p>All primary server calls (and their percentage of total) incurred in the current usage period. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Secondary Calls (%) </p> </td> 
   <td colname="col2"> <p>All secondary server calls (and their percentage of total) incurred in the current usage period. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile Primary (%) </p> </td> 
   <td colname="col2"> <p>All mobile primary server calls (and their percentage of total) incurred in the current usage period. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile Secondary (%) </p> </td> 
   <td colname="col2"> <p>All mobile secondary server calls (and their percentage of total) incurred in the current usage period. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Download Usage Report {#section_D7345660B5E043CD8850954216509A3D}

This option lets you download current usage data, and data from time periods prior to the current usage period (going back to January 2015). The report downloads as a .csv file.

1. Select at least one report suite. 
1. Click **[!UICONTROL Download Report]**.

   ![](assets/download_report.png)

    <table id="table_7ADC98C9C6D94303AF4814EA4698A183"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Report Element </th> 
    <th colname="col2" class="entry"> Description </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>File Name </p> </td> 
    <td colname="col2"> <p>Hardcoded name: Usage Report &lt;<i>day and time of report creation</i>&gt;.csv </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Included Report Suites </p> </td> 
    <td colname="col2"> <p>Any report suites you selected on the Report Server Usage page are included in this list. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Included Call Types </p> </td> 
    <td colname="col2"> <p>Specify any combination of these: <span class="uicontrol"> All Calls </span> (Default), <span class="uicontrol"> Primary </span>, <span class="uicontrol"> Secondary </span>, <span class="uicontrol"> Mobile Primary </span>, <span class="uicontrol"> Mobile Secondary </span>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Time Range </p> </td> 
    <td colname="col2"> <p>You can choose the current usage period or specify a custom range. </p> <p>For a custom range, specify the <span class="uicontrol"> Range Start </span> and the <span class="uicontrol"> Range End </span>. Note that you cannot download usage data prior to January 2015. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Click **[!UICONTROL Download]**.

