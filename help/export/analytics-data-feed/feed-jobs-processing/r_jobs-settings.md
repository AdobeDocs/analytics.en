---
description: When you set up a feed, Some settings determine how often jobs are processed.
keywords: Data Feed;job;settings;daily;hourly;Data Backfills for Hourly Data Feeds;backfill
seo-description: When you set up a feed, Some settings determine how often jobs are processed.
seo-title: Jobs Settings
solution: Analytics
title: Jobs Settings
uuid: efab8ae9-d9a8-4ccf-a41a-3e697140ab62
index: y
internal: n
snippet: y
translate: y
---

# Jobs Settings


>Use the following settings to configure job processing times. These settings are set at the feed level, not the job level. 



><table id="table_2070F73212F245E98DADC6B5DFDB1C72"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Daily </td> 
   <td colname="col2"> <p>Data for each day is delivered in a single zipped file. This file has a 2GB size limit. If the file is larger than 2GB of uncompressed data, additional files are created. You receive a single delivery of all files for each day. </p> <p>Each file is named with the following format: </p> <p> <span class="filepath"> <span class="varname"> reportsuite</span>-<span class="varname"> date</span>.tar</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hourly (Default) </td> 
   <td colname="col2"> <p>Data for each hour is delivered in a single zipped file that contains all data received during that hour. You receive 24 separate deliveries for each day, with each file delivered after the data for that hour is processed. </p> <p>The term “hourly” describes the time frame of the data that is sent with each individual data export, and not the time frame in which the delivery occurs. Hourly data feeds are processed and delivered in a best-effort fashion. </p> <p>For hourly data feeds the expectation is that 95% of the time the feed will deliver within 12 hours of the close of that hour’s worth of data. Data feeds for report suites with high traffic volume may take longer to process and deliver. </p> <p>Receiving an hourly data feed is different then receiving daily feed with multiple file delivery. When receiving hourly data feeds the data for each day is split into 24 files based on the data collected during that hour, and each file is delivered as soon as it is available. A daily feed that is delivered in multiple files is delivered once per day after the previous day's data is processed, and is spilt into 2GB increments based on the amount of data collected. </p> <p>Each file is named with the following format: </p> <p> <span class="filepath"> <span class="varname"> reportsuite</span>-<span class="varname"> date</span>-<span class="varname"> hour</span>.tar</span> </p> <p>See <a href="../../analytics-data-feed/datafeeds_contents/jobs-faq.md#concept_7C67A012CCF64B0C8DA33E5A6CF7FD9E" format="dita" scope="local"> Jobs FAQ</a> for more information about factors that can impact hourly feeds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data Backfills for Hourly Data Feeds </td> 
   <td colname="col2"> <p>If you request data for earlier dates when setting up a new hourly data feed, data for dates more than 60 days ago might be delivered in daily format instead of hourly. </p> <p>In this case, you will not receive 24 separate deliveries for these days, instead, you will receive a single delivery with a midnight timestamp that contains all of the data for that day. If you are requesting this type of backfill, Make sure your ETL is configured to process daily deliveries. </p> </td> 
  </tr> 
 </tbody> 
</table>

