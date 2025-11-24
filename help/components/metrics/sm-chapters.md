---
title: Streaming media services chapter metrics
description: Available metrics when you enable [!UICONTROL Media Chapters] for a report suite.
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
---
# Streaming media services chapter metrics

*This page describes the available metrics when you enable [!UICONTROL Media Chapters] for a report suite. See [Streaming media services chapter dimensions](../dimensions/sm-chapters.md) for available dimensions.*

Streaming media services chapter metrics provide supplemental reporting functionality to data collection through streaming media services collection libraries. Use of these metrics require the **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Media Chapters]** under [Media reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), the following metrics are available:

| Metric name | Description | Sent with | Context data variable | XDM field |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Chapter completes]** | A boolean that triggers when a chapter completes. | Chapter Close | `a.media.chapter.complete` | `xdm.mediaReporting.`<br>`chapterDetails.isCompleted` |
| **[!UICONTROL Chapter starts]** | A boolean that triggers when a chapter starts. | Chapter Start | `a.media.chapter.view` | `xdm.mediaReporting.`<br>`chapterDetails.isStarted` |
| **[!UICONTROL Chapter time spent]** | The amount of time spent on the chapter, in seconds. | Chapter Close | `a.media.chapter.timePlayed` | `xdm.mediaReporting.`<br>`chapterDetails.timePlayed` |
