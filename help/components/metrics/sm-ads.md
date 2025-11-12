---
title: Streaming media services ad metrics
description: Available metrics when you enable [!UICONTROL Media Ads] for a report suite.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
---
# Streaming media services ad metrics

*This page describes the available metrics when you enable [!UICONTROL Media Ads] for a report suite. See [Streaming media services ad dimensions](../dimensions/sm-ads.md) for available dimensions.*

Streaming media services ad metrics provide supplemental reporting functionality to data collection through streaming media services libraries. Use of these metrics require the **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Media Ads]** under [Media reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), the following metrics are available:

| Metric name | Description | Sent with | Context data variable | XDM field |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Ad completes]** | Triggered when a video ad completes. | Ad Close | `a.media.ad.complete` | `xdm.mediaReporting.`<br>`advertisingDetails.isCompleted` |
| **[!UICONTROL Ad starts]** | Triggered when a video ad starts. | Ad Start | `a.media.ad.view` | `xdm.mediaReporting.`<br>`advertisingDetails.isStarted` |
| **[!UICONTROL Ad time spent]** | The total amount of time spent watching the ad, in seconds. | Ad Close | `a.media.ad.timePlayed` | `xdm.mediaReporting.`<br>`advertisingDetails.timePlayed` |
| **[!UICONTROL Media time spent]** | Sums the event duration for all '[!UICONTROL Play]' events (both main and ad content), in seconds. | Media Close | `a.media.totalTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.totalTimePlayed` |
