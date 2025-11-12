---
title: Streaming media services core dimensions
description: Available dimensions when you enable [!UICONTROL Media Core] for a report suite.
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
---
# Streaming media services core dimensions

*This page describes the available dimensions when you enable [!UICONTROL Media Core] for a report suite. See [Streaming media services core metrics](../metrics/sm-core.md) for available metrics.*

Streaming media services core dimensions provide basic reporting functionality to data collected through streaming media services libraries. Use of these dimensions require the **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Media Core]** under [Media reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), the following dimensions are available:

| Dimension name | Description | Sent with | Context data variable | XDM field |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Content]** | Content ID of the content. | Media Start, Media Close | `a.media.`<br>`name` | `xdm.mediaCollection.`<br>`sessionDetails.name`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.name` |
| **[!UICONTROL Content channel]** | The distribution station or channel where the content is played. Any string value is valid. | Media Start, Media Close | `a.media.`<br>`channel` | `xdm.mediaCollection.`<br>`sessionDetails.channel`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.channel` |
| **[!UICONTROL Content length (variable)]** | The maximum length (or duration) of the content consumed, in seconds. This dimension is required for several metrics, including '[!UICONTROL Average minute audience]'. If this dimension is not set, dependent metrics are not available.<br><br>A classification dimension named '[!UICONTROL Video length]' is also available, which provides a similar purpose. This dimension and the classification are treated as two distinct dimensions. | Media Start, Media Close | `a.media.`<br>`length` | `xdm.mediaCollection.`<br>`sessionDetails.length`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.length` |
| **[!UICONTROL Content name (variable)]** | The friendly name of the content. A classification named '[!UICONTROL Video name]' is also available, which provides a similar purpose. This dimension and the classification are treated as two distinct dimensions. | Media Start, Media Close | `a.media.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`sessionDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.friendlyName` |
| **[!UICONTROL Content player name]** | The name of the content player. | Media Start, Media Close | `a.media.`<br>`playerName` | `xdm.mediaCollection.`<br>`sessionDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.playerName` |
| **[!UICONTROL Content segment]** | The interval that describes the part of the content that has been viewed, in minutes. The segment is computed as min and max of the playhead values during a playback session. | Media Close | `a.media.`<br>`segment` | `xdm.mediaReporting.`<br>`sessionDetails.segment` |
| **[!UICONTROL Content type]** | The type of content. Valid values include `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD`, or a custom value. | Media Start, Media Close | `a.contentType` | `xdm.mediaCollection.`<br>`sessionDetails.contentType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.contentType` |
| **[!UICONTROL Media path]** | The path that the visitor took to reach the content. | Media Start | `a.media.path` | |
| **[!UICONTROL Stream type]** | The stream type. Valid values include `audio` and `video`. | Media Start, Media Close | `a.media.`<br>`streamType` | `xdm.mediaCollection.`<br>`sessionDetails.streamType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.streamType` |

In addition to the above dimensions, Adobe automatically creates the following classification dimensions. You must upload classification data to view reports that use these dimensions.

| Classification name | Parent dimension | Description |
| --- | --- | --- |
| **[!UICONTROL Video length]** | [!UICONTROL Content] | The maximum length (or duration) of the content consumed, in seconds. Metrics that depend on content length cannot use this classification; you must create a calculated metric to obtain metrics such as '[!UICONTROL Average minute audience]' using this classification. |
| **[!UICONTROL Video name]** | [!UICONTROL Content] | The friendly name of the content. It is the classification equivalent of '[!UICONTROL Content name (variable)]'. |
