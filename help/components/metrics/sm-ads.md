---
title: Streaming Media ad metrics
description: Available metrics when you enable [!UICONTROL Media Ads] for a report suite.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
---
# Streaming Media ad metrics

*This page describes the available metrics when you enable [!UICONTROL Media Ads] for a report suite. See [Streaming Media ad dimensions](../dimensions/sm-ads.md) for available dimensions.*

Streaming Media ad metrics provide supplemental reporting functionality to data collection through streaming media collection libraries. Use of these metrics require the **[!UICONTROL Adobe Streaming Media Collection]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Media Ads]** under [Media reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), the following metrics are available:

| Metric name | Description | Sent with | Context data variable |
| --- | --- | --- | --- |
| Ad completes | Triggered when a video ad completes. | Ad Close | `a.media.ad.complete` |
| Ad starts | Triggered when a video ad starts. | Ad Start | `a.media.ad.view` |
| Ad time spent | The total amount of time spent watching the ad, in seconds. | Ad Close | `a.media.ad.timePlayed` |
| Media time spent | Sums the event duration for all PLAY events (both main and ad content), in seconds. | Media Close | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
