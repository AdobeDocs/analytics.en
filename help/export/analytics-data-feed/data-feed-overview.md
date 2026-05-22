---
description: Learn how to use data feeds to get raw data out of Adobe Analytics. Find out the prerequisites for using data feeds what to do next.
keywords: clickstream;data feed;datafeed;Data Feed
title: Analytics Data Feed Overview
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
TQID: 'https://experienceleague.adobe.com/XVFQdMEfIM7lQlnU3b-zRbQ9-RliqtaBjr-7ptxkI1o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: ede9f3ba-4ee4-4497-9d8e-e9da5848bda0
    internal-label: Data feeds
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
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

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Navigate the data feed interface](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/exporting/data-feeds/data-feeds-management-ui){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Find your data feed id](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/exporting/data-feeds/find-your-data-feed-id){target="_blank"} for a demo video.

>[!ENDSHADEBOX]
