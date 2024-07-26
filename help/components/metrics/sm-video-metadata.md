---
title: Streaming Media video metadata metrics
description: Available metrics when you enable [!UICONTROL Video Metadata] for a report suite.
feature: Metrics
---
# Streaming Media video metadata metrics

*This page describes the available metrics when you enable [!UICONTROL Video metadata] for a report suite. See [Streaming Media video metadata dimensions](../dimensions/sm-video-metadata.md) for available dimensions.*

Streaming Media video metadata metrics provide supplemental reporting functionality to data collection through streaming media collection libraries. Use of these metrics require the **[!UICONTROL Adobe Streaming Media Collection Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Video Metadata]** under [Media reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), the following metric is available:

| Metric name | Description | Sent with | Context data variable |
| --- | --- | --- | --- |
| Authorized | A boolean that triggers when the user is authorized through Adobe authentication. | Media Start, Media Close | `a.media.pass.auth` |

{style="table-layout:auto"}
