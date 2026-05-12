---
title: Streaming media services ad metrics
description: Available metrics when you enable [!UICONTROL Media Ads] for a report suite.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
TQID: https://experienceleague.adobe.com/I4CXBdLXx-dS1lZAVSfno-rbEkLKWxNccLwP58HSNzk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
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
