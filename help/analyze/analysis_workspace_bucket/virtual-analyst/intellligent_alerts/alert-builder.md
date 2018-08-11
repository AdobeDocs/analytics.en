---
description: null
seo-description: null
seo-title: Alert Builder
title: Alert Builder
uuid: 6813169b-7cd5-4858-a23a-b10258820562
index: y
internal: n
snippet: y
translate: y
---

# Alert Builder

Access the Alert Builder in one of four ways: 

* By using the following shortcut in Analysis Workspace: ` ctrl (or cmd) + shift + a` 

* By going to ** [!UICONTROL  Workspace] ** > ** [!UICONTROL  Components] ** > ** [!UICONTROL  New Alert] **.
* By selecting one or more freeform table line items, right-clicking and selecting ** [!UICONTROL  Create Alert from Selection] **.
* From within a Reports &amp; Analytics report, by going to ** [!UICONTROL  More] ** > ** [!UICONTROL  Add Alert] **.
The Alert Builder interface is familiar to those who have built segments or calculated metrics in Analytics: 

![](../../../assets/alert_builder.png) 

<table id="table_FFAA317BB96D4C389650243F71D99BD4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting Name </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Alert Name </p> </td> 
   <td colname="col2"> <p>Specify a name for the alert. The alert name might contain the name of the report or the metrics threshold. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Time Granularity </p> </td> 
   <td colname="col2"> <p>Specify when you want the metric to be checked: Hourly, Daily, Weekly, or Monthly. </p> <p>Note:  For report suites with a custom calendar, we do not support monthly granularity in the Alert Builder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recipients </p> </td> 
   <td colname="col2"> <p>Specify where the alert can be sent. An alert can be sent to an Analytics user, an Analytics group, a raw email address, or to a phone number. <p type="important">Note: The phone number must be preceded by a "+" and a <a href="https://countrycode.org/" format="https" scope="external"> country code</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration Date </p> </td> 
   <td colname="col2"> <p>Set the alert's expiration date. </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <p>Send an Alert When... </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>... Any of These Metrics trigger </p> </td> 
   <td colname="col2"> <p>Drag and drop metrics into the canvas that will add triggers. </p> <p>Note: An <b>"incompatible components”</b> message will appear if not all the components (metrics/dimensions/segments) in the alert are compatible with the currently selected report suite. </p> <p>Determine the threshold that the metric must exceed before an alert is set. You can set this value to a threshold and then to one of the following conditions: </p> 
    <ul id="ul_381B5484577E46E293638EB78E7FAF0A"> 
     <li id="li_F76491EF23C54ED5A85F337EB3E85422">anomaly exists </li> 
     <li id="li_FD0F08AA2BFF4675A97CAB5B243FC10F">anomaly is above expected </li> 
     <li id="li_5F0E6AF53A634959B3E7BC2798E1029D">anomaly is below expected </li> 
     <li id="li_87830B91CBEE4ABC9652E235B3A365DD">anomaly exceeds </li> 
     <li id="li_418DB02C35354CAB94995BB6F699D322">is above or equals </li> 
     <li id="li_C39FEDDF90444EEBB99BE0A4A68622A1">is below or equals </li> 
     <li id="li_6A2064BB8D08436DA734024AEDFB76A3">changes by </li> 
    </ul> <p>"Anomaly exceeds" is a new condition that goes beyond the existing (static) thresholds. It pulls in Anomaly Detection algorithms that dynamically define the trigger. You can set a threshold of 90%, 95%, 99%, 99.75%, and 99.9%. </p> <p> Hourly granularities are set at a 99.75% threshold, and daily granularities at 99%. </p> <p>Note that you can also use calculated metrics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>... With These Filters </p> </td> 
   <td colname="col2"> <p>Drag and drop segments or dimensions to add filters. For example, adding a "Mobile Devices Only" segment would mean that the rule triggers only for mobile devices. </p> <p>Additional filters will be added using an AND statement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Add a rule </p> </td> 
   <td colname="col2"> <p>You can add AND or OR rules by clicking the gear icon. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Alert preview {#section_10D75BA7B77E4C5FAF58A719C082E070}

The interactive alert preview shows you how often, approximately, an alert will fire based on past experience. 

For example, if you set the time granularity to daily, the preview can tell you that the alert would have been triggered for a certain metric x times during the last 30 or 31 days. 

If you find that too many alerts would have been triggered, you can adjust the threshold in the [ Alert Manager](../../../analysis_workspace_bucket/virtual-analyst/intellligent_alerts/alert-manager.md#concept_633AE746900B44D2A7045386B526ED8D). 

![](../../../assets/alert_preview.png) 
