---
title: Streaming Media player state tracking metrics
description: Available metrics when you enable [!UICONTROL Player State Tracking] for a report suite.
feature: Metrics
---
# Streaming Media player state tracking metrics

Streaming Media player state tracking metrics provide supplemental reporting functionality to data collection through streaming media collection libraries. Use of these metrics require the **[!UICONTROL Adobe Streaming Media Collection Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Player State Tracking]** under [Media reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), the following metrics are available:

| Metric name | Description | Sent with | Context data variable |
| --- | --- | --- | --- |
| Streams impacted by closed captioning | Triggered if at least one Closed Captioning state happened during a playback session. | Media Close | `a.media.states.closedcaptioning.set` |
| Closed captioning counts | The number of times that the video entered a Closed Captioning state. | Media Close | `a.media.states.closedcaptioning.count` |
| Closed captioning total duration | The amount of time that the video was in a Closed Captioning state, in seconds. | Media Close | `a.media.states.closedcaptioning.time` |
| Streams impacted by full screen | Triggered if at least one Full Screen state happened during a playback session. | Media Close | `a.media.states.fullscreen.set` |
| Full screen counts | The number of times that the video entered a Full Screen state. | Media Close | `a.media.states.fullscreen.count` |
| Full screen total duration | The amount of time that the video was in a Full Screen state, in seconds. | Media Close | `a.media.states.fullscreen.time` |
| Streams impacted by in focus | Triggered if at least one In Focus state happened during a playback session. | Media Close | `a.media.states.infocus.set` |
| In focus counts | The number of times that the video entered an In Focus state. | Media Close | `a.media.states.infocus.count` |
| In focus total duration | The amount of time that the video was in an In Focus state, in seconds. | Media Close | `a.media.states.infocus.time` |
| Streams impacted by mute | Triggered if at least one Mute state happened during a playback session. | Media Close | `a.media.states.mute.set` |
| Mute counts | The number of times that the video entered a Mute state. | Media Close | `a.media.states.mute.count` |
| Mute total duration | The amount of time that the video was in a Mute state, in seconds. | Media Close | `a.media.states.mute.time` |
| Streams impacted by picture in picture | Triggered if at least one Picture In Picture state happened during a playback session. | Media Close | `a.media.states.pictureinpicture.set` |
| Picture in picture counts | The number of times that the video entered a Picture In Picture state. | Media Close | `a.media.states.pictureinpicture.count` |
| Picture in picture total duration | The amount of time that the video was in a Picture In Picture state, in seconds. | Media Close | `a.media.states.pictureinpicture.time` |

{style="table-layout:auto"}
