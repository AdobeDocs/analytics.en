---
description: Data warehouse provides a flexible interface to run custom reports. Following these guidelines can help reduce the time it takes to retrieve data.
keywords: best practices;failure;timeout;troubleshooting
seo-description: Data warehouse provides a flexible interface to run custom reports. Following these guidelines can help reduce the time it takes to retrieve data.
seo-title: Data Warehouse best practices
solution: Analytics
title: Data Warehouse best practices
topic: Data warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
index: y
internal: n
snippet: y
---

# Data Warehouse best practices

Data warehouse provides a flexible interface to run custom reports. Following these guidelines can help reduce the time it takes to retrieve data.

<table id="table_B59B923864C64EAC85BCB0DF9F6E481C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Guideline </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Run Page Views, Visits, Visitors, and other standard reports in Reports &amp; Analytics </td> 
   <td colname="col2"> <p>Before creating a Data warehouse report, see if the information you are looking for is already available in reports. If so, the report will be delivered much faster due to the pre-processing performed by Reports &amp; Analytics for common metrics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Understand the amount of data you are requesting </td> 
   <td colname="col2">A multi-year report on a large report suite can contain tens of billions of data rows. Processing and evaluating this data can take days, or even weeks. <p>Evaluate how the report is being used to determine if some of the multi-year data is available, or if you can break the report into multiple requests. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Match the report period to the granularity </td> 
   <td colname="col2"> Reporting granularity requires additional processing time. If you are reporting monthly granularity for an entire year, your reports process much faster if you submit a report request for each month. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report on completed data ranges </p> </td> 
   <td colname="col2"> <p>Data warehouse reports are generated when the date range requested is complete. For example, if you request a report for the current week on Wednesday, the report isn't generated until Sunday of the following week. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Generate pathing reports in data warehouse </td> 
   <td colname="col2"> Pathing metrics (entries, exits, bounces, etc) are not available in data warehouse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Virtual report suites </td> 
   <td colname="col2"> Data Warehouse reporting on virtual report suites supports the alternative time zone configured on the virtual report suite. </td> 
  </tr> 
 </tbody> 
</table>

