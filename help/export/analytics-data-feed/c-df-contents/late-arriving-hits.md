---
title: Late-arriving hits
description: Learn how data feeds treat late-arriving hits.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
---
# Late arriving hits {#late-arriving-hits}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_late_hits"
>title="Allow late-arriving hits"
>abstract="Select this option to include data that arrived after the data feed job finished processing data within the set reporting frequency (usually daily or hourly). With this option enabled, every time a data feed processes data, it looks at any late hits that arrived and batches them in with the next data feed file that is sent."

<!-- markdownlint-enable MD034 -->

## Understand late-arriving hits

Historical data can arrive after a data feed job finishes processing for a given hour or day, such as through timestamped hits or data sources. 

When a data feed normally processes data, it only looks at data within its reporting window (typically the most recent hour or day). If data arrives after a feed finished processing that reporting window, that data is never included in any data feed.

With late-arriving hits enabled, the processing method changes to include this data. Every time a data feed processes data, it looks at any late hits that have arrived and batches them in the next data feed file that is sent.

## Enable late-arriving hits

Before enabling the option to allow late-arriving hits for a data feed, consider the following:

* Data for different days frequently appear in data feeds when late-arriving hits are enabled. Make sure the platform that you use to ingest data feeds can accommodate data from different days within the same file.
* If a data feed file is reprocessed, the late-arriving hits that were included in the original file are included in the reprocessed file when reprocessing occurs within the first 5 days. After 5 days, late-arriving hits are not included in the reprocessed file.

You can enable late-arrive hits when creating or editing a data feed by enabling the option, **[!UICONTROL Allow late-arriving hits]**, as described in [Create a data feed](/help/export/analytics-data-feed/create-feed.md). 
