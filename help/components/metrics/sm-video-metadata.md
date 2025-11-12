---
title: Streaming media services video metadata metrics
description: Available metrics when you enable [!UICONTROL Video Metadata] for a report suite.
feature: Metrics
exl-id: b2f60a34-e139-4498-bf71-74d291759ef2
---
# Streaming media services video metadata metrics

*This page describes the available metrics when you enable [!UICONTROL Video metadata] for a report suite. See [Streaming media services video metadata dimensions](../dimensions/sm-video-metadata.md) for available dimensions.*

Streaming media services video metadata metrics provide supplemental reporting functionality to data collection through streaming media services libraries. Use of these metrics require the **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Video Metadata]** under [Media reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), the following metric is available:

| Metric name | Description | Sent with | Context data variable | XDM field |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Authorized]** | A boolean that triggers when the user is authorized through Adobe authentication. | Media Start, Media Close | `a.media.pass.auth` | `xdm.mediaCollection.`<br>`sessionDetails.authorized`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.authorized` |
