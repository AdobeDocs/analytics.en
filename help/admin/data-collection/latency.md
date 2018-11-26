---
description: The following information may help troubleshoot report suite latency issues in Analytics data.
keywords: missing data;slow
seo-description: The following information may help troubleshoot report suite latency issues in Analytics data.
seo-title: Data availability troubleshooting
solution: Analytics
subtopic: Current data
title: Data availability troubleshooting
topic: Reports
uuid: 1f0e67e3-6cea-4af8-8b18-7ae9223df7c8
index: y
internal: n
snippet: y
---

# Data availability troubleshooting

The following information may help troubleshoot report suite latency issues in Analytics data.

## Understanding Data Batching {#section_F1F009627DEE4C80AA5D0AD3F7A3C8AC}

To understand if data is latent, it is important to understand how Analytics processes data.

Each data collection server captures and processes raw analytics data, and then uploads batched data on an hourly basis for reporting. The transfer process typically takes 30 minutes, so normal latency for traffic that occurs directly after the previous upload process completes is around 90 minutes (60 minutes until the next batch upload occurs, then 30 minutes for file transfer and display). For traffic that occurs directly before an upload, data latency could drop to 30 minutes (0 minutes until the next batch upload occurs, then 30 minutes for file transfer and display).

If needed, Adobe Customer Care can enable 30 minute batched data uploads (instead of hourly) for your top report suites.

You can typically expect to see complete data in reports 2 hours after the data is collected.

## What Contributes to Latency? {#section_A712E8EA543A4B5B967982C14220D628}

Latency does not affect data collection, and its severity (how current the data is) and length (the time it takes to resolve) can vary greatly. However, it is usually limited to a single report suite.

Latency is caused by one of following general categories:

* Unexpected traffic spike: This occurs when more data is sent to a report suite than was contractually committed or expected. It is the most common cause of latency. 
* Normal hardware issues: We employ best-in-class strategies for data center management and monitoring, data redundancy, and hardware reliability. Hardware is updated on a regular basis and in conjunction with published maintenance windows. Emergency maintenance of failing hardware may require a necessary and temporary halt in data processing (not in data collection) as replacement hardware is brought online. This temporary halt in processing can result in noticeable latency. 
* Abnormal data: Unnatural data patterns, such as unusually long visits caused by a bot or spider, can temporarily increase certain processing loads that result in latency.

For more information on report suite latency, see [this Knowledge Base article](https://helpx.adobe.com/analytics/using/latency.html).

## Ways to Mitigate or Prevent Latency {#section_575648AC01B9415A98A00DD2F9C8813F}

Several strategies exist to prevent latency or decrease recovery time when it occurs:

* Notify Adobe of expected traffic spikes: While it is impossible to anticipate every traffic spike to your site, there may be cases where you are expecting to receive a significant increase in traffic (such as during a particularly successful holiday period or shortly after a large campaign push). In these cases, Adobe provides a way for your organization to inform us of expected traffic increases so that we can allocate additional processing resources to your report suite. 
* Consider processing load when activating new features: Some features are more processing intensive than others. The more features enabled on a report suite, the more difficult it is to recover from latency. When enabling features on a report suite, keep in mind the following features that increase the amount of data to process:

    * Implementing many success events on the same page 
    * More than 5 events with participation enabled 
    * Commerce Visits and Visitors 
    * Complex VISTA rules 
    * More than 20 values in the products variable 
    * Event serialization

* Enable IAB Bot filtering: [Bot filtering](https://marketing.adobe.com/resources/help/en_US/admin/index.html?f=c_bot_rules) can greatly reduce latency if your report suite is frequented by bots or spiders. It is recommended to use the IAB bot list, as it is updated and maintained by the [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). Additionally a user can customize their own bot rules to complement those from the IAB.

## What to do about Latency {#section_7A9E70F4EF1847A4A432FB9DB04FA333}

In cases where latency occurs, rest assured we pro-actively monitor our processing pipeline and will do everything we can to return processing time back to normal as quickly as possible. Many latency issues are resolved within hours. If you are concerned with a specific report suite, one of your organization's supported users can contact Customer Care with the report suite ID that is experiencing latency. The Adobe representative can validate the latency and inform you as the issue improves and is resolved.

## Data Latency as a Result of A4T Configuration {#section_806CE36354FC4C539A0DED9266A5C704}

After the A4T integration is enabled in Adobe Target, you will experience an additional 5-10 minutes of latency in Adobe Analytics. This latency increase allows data from Analytics and Target to be stored on the same hit, allowing you to break down tests by page and site section.

This increase is reflected in all Adobe Analytics services and tools, including the live stream and real-time reporting, and applies in the following scenarios:

* For live stream, real-time reports & API requests, and current data for traffic variables, only hits with a supplemental data ID are delayed. 
* For current data on conversion metrics, finalized data, and data feeds, all hits are delayed an additional 5-7 minutes.

Be aware that the latency increase starts after you implement the Experience Cloud ID service, even if you have not fully implemented this integration. 
