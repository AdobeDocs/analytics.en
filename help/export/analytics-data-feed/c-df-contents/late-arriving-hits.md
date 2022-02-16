---
title: Late arriving hits
description: Learn how data feeds treat late arriving hits.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
---
# Late arriving hits

Historical data can arrive after a data feed job finishes processing for a given hour or day, such as through timestamped hits or data sources. Late arriving hits is a backend customization setting provided by Adobe to help include this data in data feeds.

## How late arriving hits work

When a data feed normally processes data, it only looks at data within its reporting window (typically the most recent hour or day). If data arrives after a feed finished processing that reporting window, that data is never included in any data feed.

With late arriving hits enabled, the processing method changes to include this data. Every time a data feed processes data, it looks at any late hits that have arrived and batches them in the next data feed file sent to your FTP site.

## Enabling late arriving hits

Late arriving hits can be manually enabled by Adobe on individual data feeds. Before doing so, consider the following:

* Data for different days frequently appear in data feeds when late arriving hits are enabled. Make sure the platform that you use to ingest data feeds can accommodate data from different days within the same file.
* Late arriving hits increases processing time. Typically this delay is less than hour, but can be several hours or more if your report suite receives a large number of late arriving hits. Adobe recommends against enabling this setting if timely arrival for data feeds is imperative to your organization's workflow.
* If a data feed file is reprocessed, the late arriving hits that were included in the original file are not included in the reprocessed file.

If you would like to enable late arriving hits for an existing recurring data feed, have a supported user contact Customer Care and include the following:

* A note that you would like to enable late arriving hits for a specific data feed
* Report suite ID
* Data feed name
