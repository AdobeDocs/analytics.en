---
description: Add or manage server all usage alerts. When you set up an alert, it applies to all report suites in all login companies of a Billing company.
seo-description: Add or manage server all usage alerts. When you set up an alert, it applies to all report suites in all login companies of a Billing company.
seo-title: Server Call Usage alerts
title: Server Call Usage alerts
uuid: 701fd542-5b24-42df-97a0-08e10929fa48
index: y
internal: n
snippet: y
---

# Server Call Usage alerts

Add or manage server all usage alerts. When you set up an alert, it applies to all report suites in all login companies of a Billing company.

A new alert category called **[!UICONTROL Server Calls Usage Alert]** will be added to the existing [Alert Management](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/intellligent_alerts.html) user interface.

It is pre-populated with **1 default alert** that would show up within any login company that has access to the Server Call Usage feature. This alerts will trigger a notification addressed to all their admins if one of the following criteria is satisfied:

* "Any" server call usage that "is above or equals" 100% for any server-call type you are entitled to, OR 
* "Any" server call usage that "is above or equals" 90% for any server-call type you are entitled to, OR 
* "Any" server call usage that "is above or equals" 75% for any server-call type you are entitled to, AND "Usage period spent" "is below or equals" 75% of Usage period.

![](assets/alerts.png)

You can access server call usage alerts in two ways:

* Click **[!UICONTROL Manage Alerts]** in the upper right corner on the Current Usage tab or the Report Suite usage tab, or 
* Navigate to **[!UICONTROL Components]** > **[!UICONTROL Alerts]** in Adobe Analytics.

## Create Server Call Usage Alerts {#section_2A2882C6D48D47C1944D52FB7C766BEC}

To create additional alerts,

1. Click **[!UICONTROL + Add]** and select **[!UICONTROL Server Call Usage Alert]**.

   ![](assets/server_call_alert.png)

1. Define the alert.

   ![](assets/sc_alert.png)

<table id="table_B855DB561EC9473EAC5A838389075606"> 
 <thead> 
  <tr> 
   <th class="entry" colspan="2"> Field </th> 
   <th class="entry" colspan="2"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colspan="2"> <p>Title </p> </td> 
   <td colspan="2"> <p>Specify a descriptive name. You cannot save the alert without a name. </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <p>Time Granularity </p> </td> 
   <td colspan="2"> <p>Refers to how often the alert will be checked. <b>We support only Weekly granularity at this time.</b> This means that the alert will be checked on a weekly basis and will look back at the data from the current usage period. </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <p>Recipients </p> </td> 
   <td colspan="2"> <p>Specify anyone on the organization who should get an email when the alert triggers the specified threshold. </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <p>Expiration Date </p> </td> 
   <td colspan="2"> <p>By default, the expiration date is one year from the alert creation date. </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <p>Send an Alert When </p> </td> 
   <td colspan="2"> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> 
    <ul id="ul_B78C5BED460D4126A4E835D7489F699C"> 
     <li id="li_41251882CE7E4B1F9BE0C5A1987BBFB1">Any of These Metrics Trigger </li> 
    </ul> </td> 
   <td colspan="2"> <p>Add the type of server call/s as a metric and specify the alert threshold by selecting the modifier and the threshold: </p> 
    <ul id="ul_43E5900EDBFC4643AD88A579FEB8D3E9"> 
     <li id="li_F6BFB591CD4F41A5B7AB47902CFEE230">is above or equals </li> 
     <li id="li_FCEDF4C639014D84A30AAAFE27A06734">is below or equals </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> 
    <ul id="ul_552579F35F5C441488E69991300CF236"> 
     <li id="li_6B0095B814A54CDABD28802CD1C84AFA">With </li> 
    </ul> </td> 
   <td colspan="2"> <p>Specify the threshold and condition (is above or equals or is below or equals) for the Usage Period Spent. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Save]**.

## Manage Server Calls Usage Alerts {#section_8FF98170763C4B5CBEC6DD43F893177A}

![](assets/alert_mgmt.png)

To manage alerts:

1. Select the checkbox next to one or more alerts. The alert management actions display at the top. 
1. Complete one or more of these actions: 

<table id="table_2735B4402B9A4F6BBBFA10A1400C86A4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Action </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>+ Add </p> </td> 
   <td colname="col2"> <p>Access the <a href="../../admin/c-server-call-usage/scu-alerts.md#section_2A2882C6D48D47C1944D52FB7C766BEC" format="dita" scope="local"> Alert Builder</a> by clicking <span class="uicontrol"> + Add</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tag </p> </td> 
   <td colname="col2"> <p>Tag alerts to organize them for ease of use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Delete </p> </td> 
   <td colname="col2"> <p>You can delete all alerts except default alerts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rename </p> </td> 
   <td colname="col2"> <p>You can rename all alerts except default alerts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Approve </p> </td> 
   <td colname="col2"> <p>Approve alerts to make them "official." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enable/Disable </p> </td> 
   <td colname="col2"> <p>You can enable or disable all alerts, even the default ones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Renew </p> </td> 
   <td colname="col2"> <p> When one or more alerts are selected, they can be renewed. This extends their expiration dates to be 1 year from the day <span class="uicontrol"> Renew</span> was clicked, regardless of their original expiration date. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Export to CSV </p> </td> 
   <td colname="col2"> <p>See <a href="../../admin/c-server-call-usage/report-suite-usage.md#section_D7345660B5E043CD8850954216509A3D" format="dita" scope="local"> Download Usage Report</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

