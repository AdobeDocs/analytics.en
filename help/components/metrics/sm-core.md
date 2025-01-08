---
title: Streaming Media core metrics
description: Available metrics when you enable [!UICONTROL Media Core] for a report suite.
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
---
# Streaming Media core metrics

*This page describes the available metrics when you enable [!UICONTROL Media Core] for a report suite. See [Streaming Media core dimensions](../dimensions/sm-core.md) for available dimensions.*

Streaming Media core metrics provide basic reporting functionality to data collected through streaming media collection libraries. Use of these metrics require the **[!UICONTROL Adobe Streaming Media Collection]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Media Core]** under [Media reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), the following metrics are available:

| Metric name | Description | Sent with | Context data variable |
| --- | --- | --- | --- |
| Average minute audience | The total amount of time spent on a given piece of content, divided by its length for all of its playback sessions.<br>`[Time spent] / [Media length]` | Media Close | `a.media.averageMinuteAudience` |
| Content completes | Triggers when a piece of content completes. This metric does not necessarily mean that they viewed the entirety of the content; they could have skipped ahead. It only means that they reached the end of the content. | `a.media.complete` |
| Paused impacted streams | A boolean that triggers if one or more pauses happened during the playback of content. | Media Close | `a.media.pause` |
| Pause events | The count of pauses that happened during a playback session. | Media Close | `a.media.pauseCount` |
| Total pause duration | The total duration of all pause events, in seconds. | Media Close | `a.media.pauseTime` |
| Content starts | The first frame of media is consumed. If a user drops during an ad or during buffering, this event does not trigger. | Media Close | `a.media.play` |
| 10% progress marker | The playhead passes the 10% marker of content based on length. This marker is only counted once, even if seeking backwards. If seeking forward, skipped markers are not counted. | Media Close | `a.media.progress10` |
| 25% progress marker | The playhead passes the 25% marker of content based on length. This marker is only counted once, even if seeking backwards. If seeking forward, skipped markers are not counted. | Media Close | `a.media.progress25` |
| 50% progress marker | The playhead passes the 50% marker of content based on length. This marker is only counted once, even if seeking backwards. If seeking forward, skipped markers are not counted. | Media Close | `a.media.progress50` |
| 75% progress marker | The playhead passes the 75% marker of content based on length. This marker is only counted once, even if seeking backwards. If seeking forward, skipped markers are not counted. | Media Close | `a.media.progress75` |
| 95% progress marker | The playhead passes the 95% marker of content based on length. This marker is only counted once, even if seeking backwards. If seeking forward, skipped markers are not counted. | Media Close | `a.media.progress95` |
| Content resumes | A boolean that triggers when content is resumed after more than 30 minutes of buffer, pause, or stall period. Also triggers if set by the player on the VideoInfo trackPlay. | Media Close | `a.media.resume` |
| Content segment views | A boolean that triggers on the first frame of viewed segment. | Media Close | `a.media.segmentView` |
| Media starts | A boolean that triggers when the media initially loads. This event includes ads, buffering, and errors. | Media Start | `a.media.view` |
| Content time spent | The total event duration for all events of type PLAY on the main content, in seconds. | Media Close | `a.media.timePlayed` |
| Unique time played | The total amount of time that unique content is played, in seconds. This metric excludes time played when viewing repeat content, such as seeking backwards. | Media Close | `a.media.uniqueTimePlayed` |

{style="table-layout:auto"}
