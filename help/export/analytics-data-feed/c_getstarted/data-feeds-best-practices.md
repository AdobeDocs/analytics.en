---
description: Following are some best practices for data feed processing and delivery. You should 
keywords: Data Feed;best practices;traffic spike;hourly;ftp
seo-description: Following are some best practices for data feed processing and delivery. You should 
seo-title: Best Practices and General Information
solution: Analytics
title: Best Practices and General Information
uuid: ef7be9d1-4034-4fbf-ab95-feb747d74a30
index: y
internal: n
snippet: y
---

# Best Practices and General Information

Following are some best practices for data feed processing and delivery. You should:

* Expect data feeds to be delivered within 12 hours after the end of a given time period 95% of the time.

  For example, if you have an hourly feed, the data feed request for the 3 a.m. to 4 a.m. hour should be delivered by 4 p.m. 95% of the time. Data feeds for report suites with high traffic volume can take longer to process and deliver, particularly if they are configured as daily feeds rather than hourly feeds. 
* Ensure that you [communicate any anticipated traffic spikes](https://marketing.adobe.com/resources/help/en_US/reference/t_traffic_schedule_spike.html) ahead of time. Any upstream latency has a direct impact on how quickly the data feed process can get started. 
* Ensure that you have ample room on your FTP site. Clean it out on a regular basis so that you don’t inadvertently run out of disk space. 
* When changing FTP credentials, please ensure that the credentials are current in Adobe's data feed system. 
* Use hourly delivery if possible. It makes the files smaller and faster to produce/transmit. 
* Consider using “multiple-file” delivery (typically done with large daily feeds.) Multiple-file delivery breaks the single monolithic file into smaller files and delivers them all at the same time. Again, smaller files make it faster to create, zip/unzip, and transmit the data. 
* If you are using sFTP as the delivery method, do not read and do not delete files with a “.part” suffix. The “.part” suffix indicates the file is partially transferred, it is not complete. Once the file has been transferred, the file will be renamed without the “.part” suffix. 
* Build your ETL process with the assumption that, occasionally, a file may be transferred more than once. Otherwise, you may end up with duplicate data. 
* Exporting [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/) data (contextData) via Analytics Data Feed is not supported.

