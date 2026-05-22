---
description: There are visitor metrics in Adobe Analytics and Adobe Audience Manager that have similar definitions, and but that are not 100% aligned, for various reasons.
title: Visitor Count differences
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
TQID: 'https://experienceleague.adobe.com/ksfYYDZ6G9vH7WEZVh-JsN93Rl-jsZTe9-CQADSwnfI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
subfeature_v2:
  - id: a97e0d8c-238a-47ee-8d81-16bd45309bed
    internal-label: Audience Manager integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
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
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html"  > Adobe Audience Manager: Total Segment Population</a> </p> </td> 
   <td colname="col3"> <p>Count of devices (Experience Cloud IDs) that were a member of your segment during the lookback period. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html"  > Adobe Audience Manager: Real-Time Segment Population</a> </p> </td> 
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

Adobe Audience Manager Real-time Segment Population and Analytics Visitors with Experience Cloud ID used within Audience Analytics reporting will be the most similar. For the near term however, because of several factors, there will be slight discrepancies between them. Contributing factors are: 

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Factor </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager: Real-time Segment Population </th> 
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
