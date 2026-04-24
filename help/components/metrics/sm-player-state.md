---
title: Streaming media services player state tracking metrics
description: Available metrics when you enable [!UICONTROL Player State Tracking] for a report suite.
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
TQID: https://experienceleague.adobe.com/3juhc8fsLlyNTdeRNceLhE-LAEF9jLYiIF55YDeeUGU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
# Streaming media services player state tracking metrics

Streaming media services player state tracking metrics provide supplemental reporting functionality to data collection through streaming media services libraries. Use of these metrics require the **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Player State Tracking]** under [Media reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), the following metrics are available:

| Metric name | Description | Sent with | Context data variable | XDM field |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Streams impacted by closed captioning]** | Triggered if at least one Closed Captioning state happened during a playback session. | Media Close | `a.media.states.`<br>`closedcaptioning.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Closed captioning counts]** | The number of times that the video entered a Closed Captioning state. | Media Close | `a.media.states.`<br>`closedcaptioning.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Closed captioning total duration]** | The amount of time that the video was in a Closed Captioning state, in seconds. | Media Close | `a.media.states.`<br>`closedcaptioning.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Streams impacted by full screen]** | Triggered if at least one Full Screen state happened during a playback session. | Media Close | `a.media.states.`<br>`fullscreen.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Full screen counts]** | The number of times that the video entered a Full Screen state. | Media Close | `a.media.states.`<br>`fullscreen.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Full screen total duration]** | The amount of time that the video was in a Full Screen state, in seconds. | Media Close | `a.media.states.`<br>`fullscreen.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Streams impacted by in focus]** | Triggered if at least one In Focus state happened during a playback session. | Media Close | `a.media.states.`<br>`infocus.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL In focus counts]** | The number of times that the video entered an In Focus state. | Media Close | `a.media.states.`<br>`infocus.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL In focus total duration]** | The amount of time that the video was in an In Focus state, in seconds. | Media Close | `a.media.states.`<br>`infocus.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Streams impacted by mute]** | Triggered if at least one Mute state happened during a playback session. | Media Close | `a.media.states.`<br>`mute.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Mute counts]** | The number of times that the video entered a Mute state. | Media Close | `a.media.states.`<br>`mute.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Mute total duration]** | The amount of time that the video was in a Mute state, in seconds. | Media Close | `a.media.states.`<br>`mute.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Streams impacted by picture in picture]** | Triggered if at least one Picture In Picture state happened during a playback session. | Media Close | `a.media.states.`<br>`pictureinpicture.set` | `mediaReporting.states.`<br>`[*].isSet` |
| **[!UICONTROL Picture in picture counts]** | The number of times that the video entered a Picture In Picture state. | Media Close | `a.media.states.`<br>`pictureinpicture.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Picture in picture total duration]** | The amount of time that the video was in a Picture In Picture state, in seconds. | Media Close | `a.media.states.`<br>`pictureinpicture.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
