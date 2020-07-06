---
description: A comparison table for Analytics reporting APIs. Links to supporting documentation are provided.
title: Analytics Reporting API Comparison
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
---

# Analytics Reporting API Comparison

A comparison table for Analytics reporting APIs. Links to supporting documentation are provided.

>[!NOTE]
>
>Regarding latency, Analytics for Target (A4T) combines Analytics and Target data on the same hit for integrated reporting. Because Analytics and Target calls occur at different times, hits are stored before any processing occurs to collect data from both solutions. This process adds **an additional 7-10 minutes** of latency to all checkpoints.

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API Type </th> 
   <th colname="col2" class="entry"> Fully Processed </th> 
   <th colname="col3" class="entry"> Real-Time </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> Fully-processed, finalized data that is available in all Analytics interfaces. </td> 
   <td colname="col3"> Partially-processed, limited metrics available within seconds of collection. </td> 
   <td colname="col4"> Partially-processed hit data available within seconds of collection. </td> 
   <td colname="col5"> Fully-processed, finalized data that is used for pulling large data exports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://docs.adobe.com/content/help/en/analytics/technotes/latency.html"  > Latency</a> </p> </td> 
   <td colname="col2"> 30-90 Minutes </td> 
   <td colname="col3"> * Seconds -10 minutes </td> 
   <td colname="col4"> Seconds -10 minutes </td> 
   <td colname="col5"> 90 minutes + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processing Completion</b> </td> 
   <td colname="col2"> Full </td> 
   <td colname="col3"> Partial </td> 
   <td colname="col4"> Partial </td> 
   <td colname="col5"> Full </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://docs.adobe.com/content/help/en/analytics/landing/home.html"  > Reporting Interfaces</a> </td> 
   <td colname="col2"> Reports &amp; Analytics, Report Builder, API </td> 
   <td colname="col3"> Real-time report in Reports &amp; Analytics, Report Builder, API </td> 
   <td colname="col4"> API only </td> 
   <td colname="col5"> Data Warehouse &amp; API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Granularity</b> </td> 
   <td colname="col2"> Summarized </td> 
   <td colname="col3"> Summarized </td> 
   <td colname="col4"> Hit level </td> 
   <td colname="col5"> Summarized </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Visitor Profile Processing</b> </td> 
   <td colname="col2"> Yes </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> No </td> 
   <td colname="col5"> Yes </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Supports Segments</b> </td> 
   <td colname="col2"> Yes </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> No </td> 
   <td colname="col5"> Yes (but only Data Warehouse compatible segments) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Analytics SKU</b> </td> 
   <td colname="col2"> Standard+ </td> 
   <td colname="col3"> Standard+ </td> 
   <td colname="col4"> Premium Complete or Predictive Intelligence </td> 
   <td colname="col5"> Standard+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Documentation</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B"  > Web Services</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time"  > Real-Time Reports</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B"  > Livestream Overview</a> </p> </td> 
   <td colname="col5"> <p><a href="https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Related Help**

* [Adobe/IO](https://www.adobe.io/) - A comprehensive source for the technical documentation and tools needed to integrate Adobe technologies into your applications.
* [Data Workbench Query API](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

