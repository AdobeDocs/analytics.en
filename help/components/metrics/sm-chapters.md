---
title: Streaming Media chapter metrics
description: Available metrics when you enable [!UICONTROL Media Chapters] for a report suite.
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
---
# Streaming Media chapter metrics

*This page describes the available metrics when you enable [!UICONTROL Media Chapters] for a report suite. See [Streaming Media chapter dimensions](../dimensions/sm-chapters.md) for available dimensions.*

Streaming Media chapter metrics provide supplemental reporting functionality to data collection through streaming media collection libraries. Use of these metrics require the **[!UICONTROL Adobe Streaming Media Collection]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Media Chapters]** under [Media reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), the following metrics are available:

| Metric name | Description | Sent with | Context data variable |
| --- | --- | --- | --- |
| Chapter completes | A boolean that triggers when a chapter completes. | Chapter Close | `a.media.chapter.complete` |
| Chapter starts | A boolean that triggers when a chapter starts. | Chapter Start | `a.media.chapter.view` |
| Chapter time spent | The amount of time spent on the chapter, in seconds. | Chapter Close | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
