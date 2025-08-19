---
title: Streaming media services core dimensions
description: Available dimensions when you enable [!UICONTROL Media Core] for a report suite.
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
---
# Streaming media services core dimensions

*This page describes the available dimensions when you enable [!UICONTROL Media Core] for a report suite. See [Streaming media services core metrics](../metrics/sm-core.md) for available metrics.*

Streaming media services core dimensions provide basic reporting functionality to data collected through streaming media services libraries. Use of these dimensions require the **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Media Core]** under [Media reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), the following dimensions are available:

| Dimension name | Description | Sent with | Context data variable |
| --- | --- | --- | --- |
| Content | Content ID of the content. | Media Start, Media Close | `a.media.name` |
| Content channel | The distribution station or channel where the content is played. Any string value is valid. | Media Start, Media Close | `a.media.channel` |
| Content length (variable) | The maximum length (or duration) of the content consumed, in seconds. This dimension is required for several metrics, including 'Average minute audience'. If this dimension is not set, dependent metrics are not available.<br><br>A classification dimension named 'Video length' is also available, which provides a similar purpose. This dimension and the classification are treated as two distinct dimensions. | Media Start, Media Close | `a.media.length` |
| Content name (variable) | The friendly name of the content. A classification named 'Video name' is also available, which provides a similar purpose. This dimension and the classification are treated as two distinct dimensions. | Media Start, Media Close | `a.media.friendlyName` |
| Content player name | The name of the content player. | Media Start, Media Close | `a.media.playerName` |
| Content segment | The interval that describes the part of the content that has been viewed, in minutes. The segment is computed as min and max of the playhead values during a playback session. | Media Close | `a.media.segment` |
| Content type | The type of content. Valid values include `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD`, or a custom value. | Media Start, Media Close | `a.contentType` |
| Media path | The path that the visitor took to reach the content. | Media Start | `a.media.path` |
| Stream type | The stream type. Valid values include `audio` and `video`. | Media Start, Media Close | `a.media.streamType` |

{style="table-layout:auto"}

In addition to the above dimensions, Adobe automatically creates the following classification dimensions. You must upload classification data to view reports that use these dimensions.

| Classification name | Parent dimension | Description |
| --- | --- | --- |
| Video length | Content | The maximum length (or duration) of the content consumed, in seconds. Metrics that depend on content length cannot use this classification; you must create a calculated metric to obtain metrics such as 'Average minute audience' using this classification. |
| Video name | Content | The friendly name of the content. It is the classification equivalent of Content name (variable). |

{style="table-layout:auto"}
