---
title: Streaming Media chapter metrics
description: Available metrics when you enable [!UICONTROL Media Chapters] for a report suite.
feature: Metrics
---
# Streaming Media chapter metrics

Streaming Media chapter metrics provide supplemental reporting functionality to data collection through streaming media collection libraries. Use of these metrics require the **[!UICONTROL Adobe Streaming Media Collection Add-on]**. Contact your Adobe Account Team for details.

| Metric name | Description | Sent with | Context data variable |
| --- | --- | --- | --- |
| Chapter completes | A boolean that triggers when a chapter completes. | Chapter Close | `a.media.chapter.complete` |
| Chapter starts | A boolean that triggers when a chapter starts. | Chapter Start | `a.media.chapter.view` |
| Chapter time spent | The amount of time spent on the chapter, in seconds. | Chapter Close | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
