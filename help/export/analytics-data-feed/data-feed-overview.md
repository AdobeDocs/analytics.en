---
description: Data that is collected from web sites, mobile apps, or is uploaded using web service APIs or data sources, is processed and stored in Adobe's Data Warehouse. This raw clickstream data forms the data set that is used by Adobe Analytics.
keywords: clickstream;data feed;datafeed;Data Feed
title: Analytics Data Feed overview
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
---
# Analytics Data Feed overview

Data feeds are a powerful way to get raw data out of Adobe Analytics. This raw data can be used in other platforms outside of Adobe to use at your organization's discretion. Data is delivered in hourly batches at the conclusion of each hour, or in daily batches at the conclusion of each day.

## Prerequisites

Make sure that you meet all the following requirements before using data feeds.

* A working implementation that sends data to Adobe data collection servers. See [Validate and publish an implementation](/help/implement/launch/validate-publish-prod.md) in the Implementation guide.
* Your account is an Analytics product admin, or your account belongs to a product profile with access to data feeds.
* A bucket configured on Amazon S3, Google Cloud Platform, Azure RBAC, or Azure SAS.
* (Legacy: Required only for legacy FTP and SFTP destination types) Have an FTP site and credentials handy (FTP credentials provided by your organization.)

## Next steps

The following resources help you understand the basic workflow of obtaining data feeds. After you understand the basic workflow, you can work with teams within your organization to store or ingest raw data into a database.

* [Data feed best practices](/help/export/analytics-data-feed/data-feeds-best-practices.md): Best practices for creating and managing data feeds.
* [Create a data feed](create-feed.md): Technical details for creating a data feed, explaining individual fields in more detail
* [Manage data feeds](df-manage-feeds.md): Learn more about navigating the data feed interface
* [Data feed contents](c-df-contents/datafeeds-contents.md): Understand what is inside the compressed file <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [Data column definitions](c-df-contents/datafeeds-reference.md): A comprehensive list of all available columns.
* Video navigating the data feed interface:

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* Video on how to find your data feed ID:

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)