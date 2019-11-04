---
description: Displays the number of visits made to your entire website during a specified time period.
seo-description: Displays the number of visits made to your entire website during a specified time period.
seo-title: Visits
solution: Analytics
title: Visits
topic: Reports
uuid: ff65bddf-fb65-4cf0-8aae-4ab59c2bb0a7
---

# Visits

Displays the number of visits made to your entire website during a specified time period.

 **Report Properties**

* A visit is defined as a sequence of consecutive page views without a 30 minute break, or continuous activity for 12 hours.
* After a visit expires, a new visit is started on any subsequent image request.
* A visitor typically contains at least one (but probably more than one) visit.
* The beginning of a visit is the first image request coming from a new visitor, or after an existing user's visit has expired. This can be identified as the Entry Page.
* The end of a visit is the last image request before a visit expires. This can be identified as the Exit Page.

  See [Entries and Exits Reports](/help/components/c-variables/dimensionslist/reports-entries-exits.md).
* Hourly breakdowns are based on the report suite's time zone.
* This report does not contain line items. You view it only in the trended format.
* Granularity of hour, day, week, month, quarter, and year can be applied. These granularity settings are available depending on the reporting date range.

See [Visit Metric](/help/components/c-variables/c-metrics/metrics-visit.md) for more information about how the Experience Cloud processes this metric.

**Product Specific Report Information** 

<table id="table_3138CA443CAC4F55838216E8B8786EE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Product </th> 
   <th colname="col2" class="entry"> Navigation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Site Metrics</span> &gt; <span class="uicontrol"> Visits</span> </p> <p>You can run a <span class="wintitle"> Visits Report</span> on a selected page. Visits spanning across midnight are counted on both the day the visit started and ended. However, the total for the given date range is de-duplicated. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad Hoc Analysis </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Reports</span> &gt; <span class="uicontrol"> Site Metrics</span> &gt; <span class="uicontrol"> Visits</span> </p> 
    <ul id="ul_73FEE02C129041D6A63F2DB07676960F"> 
     <li id="li_CC3BB22DE97941EB8032BE4421FFC173"> You can break down each item in this report by almost all other reports and variables, allowing you to see breakdowns by any granularity. </li> 
     <li id="li_D53D480D73264D47945C9E1202B7BD4F">Visits spanning across midnight are counted on both the day the visit started and ended. However, the total for the given date range is deduplicated. </li> 
     <li id="li_B8BCC584F95B407DB87F5EA57CC88F62">You can use all conversion and traffic metrics in this report, as well as use different allocation for all conversion metrics. </li> 
     <li id="li_0F342D3DCFF44ABAB79BD0F9E7F43E1E">This report can use multiple highly advanced segments. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

