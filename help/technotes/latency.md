---
description: The following information can help troubleshoot report suite latency issues in Analytics data.
keywords: missing data;slow
title: Data availability and latency
feature: Data Configuration and Collection
exl-id: fedef3ea-dde6-460f-90e3-1e661ed29b78
---
# Data availability and latency in Adobe Analytics

You can typically expect to see complete data in reports 2 hours after data is collected. The following information can help troubleshoot report suite latency issues in Analytics data.

## Understanding data batching

Each data collection server captures and processes raw analytics data, and then uploads batched data on an hourly basis for reporting. The transfer process typically takes 30 minutes, so normal latency for traffic that occurs directly after the previous upload process completes is around 90 minutes (60 minutes until the next batch upload occurs, then 30 minutes for file transfer and display). For traffic that occurs directly before an upload, data latency could be as short as 30 minutes (0 minutes until the next batch upload occurs, then 30 minutes for file transfer and display).

If needed, Adobe Customer Care can enable 30 minute batched data uploads (instead of hourly) for your most-used report suites.

## Contributors to latency

Latency is a delay that is longer than the typical 2 hours it takes for data collection servers to fully process data. It does not affect data collection; data is still collected for a working implementation, regardless of how latent a report suite is. Its severity (how current the data is) and length (the time it takes to resolve) can vary greatly. It is usually limited to a single report suite.

Latency is caused by one of following general categories:

* **Unexpected traffic spike:** This type of latency occurs when more data is sent to a report suite than was contractually committed or expected. It is the most common cause of latency.
* **Normal hardware issues:** Adobe employs best-in-class strategies for data center management and monitoring, data redundancy, and hardware reliability. Hardware is updated on a regular basis and in conjunction with published maintenance windows. Emergency maintenance of failing hardware can require a necessary and temporary halt in data processing (not in data collection) as replacement hardware is brought online. This temporary halt in processing can result in noticeable latency.
* **Abnormal data:** Unnatural data patterns, such as unusually long visits caused by a bot or crawler, can temporarily increase certain processing loads that result in latency.

## Features that depend on latency

Some capabilities in the Adobe Experience Cloud come with an innate amount of latency on top of standard processing time.

* Analytics for Target (A4T) requires an additional 5-10 minutes of latency to allow collected data from both platforms to be stored in the same hit.
* Timestamped data requires additional time due to different servers this data is processed on. Timestamped hits received at or near real-time can take up to 15 minutes. Hits received with a timestamp of yesterday can take up to 2 hours. Older hits can take longer, increasing each day up to a cap of approximately 24 hours.

## Ways to mitigate or prevent latency

Several strategies exist to prevent latency or decrease recovery time when it occurs:

* **Notify Adobe of expected traffic spikes:** While it is impossible to anticipate every traffic spike to your site, there may be cases where you are expecting to receive a significant increase in traffic. Examples include a particularly successful holiday period, or shortly after a large campaign push. In these cases, Adobe provides a way for your organization to inform us of expected traffic increases so that we can allocate additional processing resources to your report suite. See [Schedule a traffic spike](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md) in the Admin user guide to learn how to notify Adobe of increased traffic.
* **Consider processing load when activating new features:** Some features are more processing intensive than others. The more features enabled on a report suite, the more difficult it is to recover from latency. When enabling features on a report suite, keep in mind the following features that increase the amount of data to process:

  * Implementing more than 20 events on the same page
  * Complex VISTA rules
  * More than 20 values in the products variable
  * Event serialization

* Enable IAB Bot filtering: [Bot filtering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md) can greatly reduce latency if your report suite is frequented by bots or crawlers. It is recommended to use the IAB bot list, as it is updated and maintained by the [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). A user can customize their own bot rules to complement those from the IAB.

## What to do about Latency

In cases where latency occurs, rest assured that Adobe proactively monitors the processing pipeline and does everything possible to return processing time back to normal as quickly as possible. Many latency issues are resolved within hours. If you are concerned with a specific report suite, one of your organization's supported users can contact Customer Care with the report suite ID that is experiencing latency. The Adobe representative can validate the latency and inform you as the issue improves and is resolved.
