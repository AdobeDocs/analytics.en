---
description: There are visitor metrics in Adobe Analytics and Adobe Audience Manager that have similar definitions, and but that are not 100% aligned, for various reasons.
title: Visitor Count differences
uuid: c3bbb887-bd02-4c1c-9a2b-64811c0ef56a
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
---
# Visitor Count differences

There are visitor metrics in Adobe Analytics and Adobe Audience Manager that have similar definitions, and but that are not 100% aligned, for various reasons.

The visitor metrics are: 

<table id="table_F9FE107A89934C3B854C55D7D76AC6E8"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Metric </th> 
   <th colname="col3" class="entry"> Definition </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/ audience-manager/user-guide/features/segments/segment-builder-data.html"  > AAM: Total Segment Population</a> </p> </td> 
   <td colname="col3"> <p>Count of devices (Experience Cloud IDs) that were a member of your segment during the lookback period. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/ audience-manager/user-guide/features/segments/segment-builder-data.html"  > AAM: Real-Time Segment Population</a> </p> </td> 
   <td colname="col3"> <p>Count of devices (Experience Cloud IDs) that were a member of your segment and reached your properties during the lookback period. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: Unique Visitors </p> </td> 
   <td colname="col3"> <p>Shows you the number of unique visitors who reached your properties during the reporting window. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: Visitors with Experience Cloud ID </p> </td> 
   <td colname="col3"> <p>Shows you the number of unique visitors with a Experience Cloud ID who reached your properties during the reporting window. </p> </td> 
  </tr> 
 </tbody> 
</table>

AAM Real-time Segment Population and Analytics Visitors with Experience Cloud ID used within Audience Analytics reporting will be the most similar. For the near term however, because of several factors, there will be slight discrepancies between them. Contributing factors are: 

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Factor </th> 
   <th colname="col2" class="entry"> AAM: Real-time Segment Population </th> 
   <th colname="col3" class="entry"> Analytics: Visitors with Experience Cloud ID </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Time zone </p> </td> 
   <td colname="col2"> <p>UTC (Coordinated Universal Time) </p> </td> 
   <td colname="col3"> <p>Specified per report suite </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom Filters </p> </td> 
   <td colname="col2"> <p>No </p> </td> 
   <td colname="col3"> <p>Yes, e.g. IP filters, bot filters </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>150-segment limit </p> </td> 
   <td colname="col2"> <p>No </p> </td> 
   <td colname="col3"> <p>Yes - Analytics counts may be affected up to 5% by the 150-segment integration limit. "Audience limit reached" will appear in the Audience Name dimension if truncation has occurred. </p> </td> 
  </tr> 
 </tbody> 
</table>

See [Understanding Segments in Analytics and Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md) for additional explanation on the nuances between Analytics and Audience Manager data and segmentation.
