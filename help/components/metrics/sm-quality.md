---
title: Streaming media services quality metrics
description: Available metrics when you enable [!UICONTROL Media Quality] for a report suite.
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
---
# Streaming media services quality metrics

*This page describes the available metrics when you enable [!UICONTROL Media Quality] for a report suite. See [Streaming media services quality dimensions](../dimensions/sm-quality.md) for available dimensions.*

Streaming media services quality metrics provide supplemental reporting functionality to data collection through streaming media services libraries. Use of these metrics require the **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Media Quality]** under [Media reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), the following metrics are available:

| Metric name | Description | Sent with | Context data variable | XDM field |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Average bitrate]** | A weighted average of all bitrate values for the play duration of a playback session. | Media Close | `a.media.qoe.`<br>`bitrateAverage` | `xdm.mediaReporting.`<br>`qoeDataDetails.bitrateAverage` |
| **[!UICONTROL Bitrate change impacted streams]** | A boolean that triggers if the bitrate changes at least once during a playback session. | Media Close | `a.media.qoe.`<br>`bitrateChange` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBitrateChangeImpactedStreams` |
| **[!UICONTROL Bitrate changes]** | The number of times that the bitrate changed. | Media Close | `a.media.qoe.`<br>`bitrateChangeCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrateChangeCount`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateChangeCount` |
| **[!UICONTROL Buffer impacted streams]** | A boolean that triggers if the video enters a Buffer state at least once. | Media Close | `a.media.qoe.`<br>`buffer` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBufferImpactedStreams` |
| **[!UICONTROL Buffer events]** | The number of times that the video buffered during a playback session. | Media Close | `a.media.qoe.`<br>`bufferCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferCount` |
| **[!UICONTROL Total buffer duration]** | The amount of time that a video spent buffering across all buffer events, in seconds. | Media Close | `a.media.qoe.`<br>`bufferTime` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferTime` |
| **[!UICONTROL Drops before start]** | A boolean that triggers if a user quits before a video's main content starts. | Media Close | `a.media.qoe.`<br>`dropBeforeStart` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`isDroppedBeforeStart` |
| **[!UICONTROL Dropped frames]** | An integer that represents the total number of frames that were dropped during a playback session. | Media Close | `a.media.qoe.`<br>`droppedFrameCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.droppedFrames`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.droppedFrames` |
| **[!UICONTROL Dropped frame impacted streams]** | A boolean that triggers when any frames are dropped during a playback session. | Media Close | `a.media.qoe.`<br>`droppedFrames` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasDroppedFrameImpactedStreams` |
| **[!UICONTROL Error impacted streams]** | A boolean that triggers when a video experiences an error at any time during a playback session. | Media Close | `a.media.qoe.`<br>`error` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasErrorImpactedStreams` |
| **[!UICONTROL Error events]** | An integer that represents the total number of errors encountered during a playback session. | Media Close | `a.media.qoe.`<br>`errorCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.errorCount` |
| **[!UICONTROL Time to start]** | The amount of time taken to start a video, in milliseconds. Adobe converts and stores this value in seconds. | Media Close | `a.media.qoe.`<br>`timeToStart` | `xdm.mediaCollection.`<br>`qoeDataDetails.timeToStart`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.timeToStart` |
