---
description: null
seo-description: null
seo-title: Enable report suite for Advertising Analytics
title: Enable report suite for Advertising Analytics
uuid: 986ba01a-6eca-41f4-b2f5-8697f4f807df
index: y
internal: n
snippet: y
---

# Enable report suite for Advertising Analytics

In order to see any Advertising Analytics search data in Analytics, you need to configure each IMS-mapped report suite for Advertising Analytics reporting.

1. [Map your report suite to an organization](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html). 
1. Navigate to **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**. 

1. Select the report suite that is [mapped to your IMS organization](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html). 
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**.

   ![](assets/aa_reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID refers to the Adobe Media Optimizer variable into which the search data is going to be inserted.

1. Set the variable allocation and expiration you want the AMO ID variable to use. Conversion variables (eVars) allow Adobe Analytics to attribute success events to specific variable values. Sometimes, variables encounter more than one value before hitting a success event. For these cases, allocation determines which variable value gets credit for the event. 

<table id="table_EF7CFF5DED4B4C2AA4B511720B12620E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Original Value (First) </p> </td> 
   <td colname="col2"> <p>The first value seen gets full allocation credit, no matter what subsequent values for that variable are. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Most Recent (Last) </p> </td> 
   <td colname="col2"> <p>The last value seen gets full allocation credit for the success event, no matter what variables were fired before it. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expire After </p> </td> 
   <td colname="col2"> <p>Lets you specify a time period, or event, after which the eVar value expires (i.e., no longer receives credit for success events). </p> <p>If a success event occurs after eVar expiration, the <span class="wintitle"> None</span> value receives credit for the event (no eVar was active). </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Enable Advertising Analytics Reporting]** (first time), or **[!UICONTROL Update Advertising Analytics Reporting]** (subsequent times). Your report suite is now ready to receive Advertising Analytics Search data. You are no ready to [create Advertising Accounts](../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md#concept_1958E8C15C334E8B9DC510EC8D5DCA7C).

