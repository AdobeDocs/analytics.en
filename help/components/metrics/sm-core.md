---
title: Streaming media services core metrics
description: Available metrics when you enable [!UICONTROL Media Core] for a report suite.
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
---
# Streaming media services core metrics

*This page describes the available metrics when you enable [!UICONTROL Media Core] for a report suite. See [Streaming media services core dimensions](../dimensions/sm-core.md) for available dimensions.*

Streaming media services core metrics provide basic reporting functionality to data collected through streaming media services collection libraries. Use of these metrics require the **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Media Core]** under [Media reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), the following metrics are available:

| Metric name | Description | Sent with | Context data variable | XDM field |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Average minute audience]** | The total amount of time spent on a given piece of content, divided by its length for all of its playback sessions.<br>`[Time spent] / [Media length]` | Media Close | `a.media.`<br>`averageMinuteAudience` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`averageMinuteAudience` |
| **[!UICONTROL Content completes]** | Triggers when a piece of content completes. This metric does not necessarily mean that they viewed the entirety of the content; they could have skipped ahead. It only means that they reached the end of the content. | | `a.media.complete` | `xdm.mediaReporting.`<br>`sessionDetails.isCompleted` |
| **[!UICONTROL Paused impacted streams]** | A boolean that triggers if one or more pauses happened during the playback of content. | Media Close | `a.media.pause` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasPauseImpactedStreams` |
| **[!UICONTROL Pause events]** | The count of pauses that happened during a playback session. | Media Close | `a.media.pauseCount` | `xdm.mediaReporting.`<br>`sessionDetails.pauseCount` |
| **[!UICONTROL Total pause duration]** | The total duration of all pause events, in seconds. | Media Close | `a.media.pauseTime` | `xdm.mediaReporting.`<br>`sessionDetails.pauseTime` |
| **[!UICONTROL Content starts]** | The first frame of media is consumed. If a user drops during an ad or during buffering, this event does not trigger. | Media Close | `a.media.play` | `xdm.mediaReporting.`<br>`sessionDetails.isPlayed` |
| **[!UICONTROL 10% progress marker]**<br>**[!UICONTROL 25% progress marker]**<br>**[!UICONTROL 50% progress marker]**<br>**[!UICONTROL 75% progress marker]**<br>**[!UICONTROL 95% progress marker]** | The playhead passes the indicated marker of content based on length. Each marker is only counted once, even if seeking backwards. If seeking forward, skipped markers are not counted. | Media Close | `a.media.progress10`<br>`a.media.progress25`<br>`a.media.progress50`<br>`a.media.progress75`<br>`a.media.progress95` | `xdm.mediaReporting.`<br>`sessionDetails.hasProgress10`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress25`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress50`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress75`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress95` |
| **[!UICONTROL Content resumes]** | A boolean that triggers when content is resumed after more than 30 minutes of buffer, pause, or stall period. Also triggers if set by the player on the VideoInfo trackPlay. | Media Close | `a.media.resume` | `xdm.mediaCollection.`<br>`sessionDetails.hasResume`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasResume` |
| **[!UICONTROL Content segment views]** | A boolean that triggers on the first frame of viewed segment. | Media Close | `a.media.segmentView` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasSegmentView` |
| **[!UICONTROL Media starts]** | A boolean that triggers when the media initially loads. This event includes ads, buffering, and errors. | Media Start | `a.media.view` | `xdm.mediaReporting.`<br>`sessionDetails.isViewed` |
| **[!UICONTROL Content time spent]** | The total event duration for all events of type PLAY on the main content, in seconds. | Media Close | `a.media.timePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.timePlayed` |
| **[!UICONTROL Unique time played]** | The total amount of time that unique content is played, in seconds. This metric excludes time played when viewing repeat content, such as seeking backwards. | Media Close | `a.media.`<br>`uniqueTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`uniqueTimePlayed` |
