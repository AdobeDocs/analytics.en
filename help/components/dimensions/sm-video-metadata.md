---
title: Streaming media services video metadata dimensions
description: Available dimensions when you enable [!UICONTROL Video Metadata] for a report suite.
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
---
# Streaming media services video metadata dimensions

*This page describes the available dimensions when you enable [!UICONTROL Video Metadata] for a report suite. See [Streaming media services video metadata metrics](../metrics/sm-video-metadata.md) for available metrics.*

Streaming media services ad dimensions provide supplemental reporting functionality to data collection through streaming media services collection libraries. Use of these dimensions require the **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Video Metadata]** under [Media reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), the following dimensions are available:

| Dimension name | Description | Sent with | Context data variable |
| --- | --- | --- | --- |
| Ad loads | The type of ad loaded. | TBD | `a.media.adLoad` |
| Day part | The time of the day when the content was broadcast or played. Any string value is supported. | Media Start, Media Close | `a.media.dayPart` |
| Episode | The episode number. | Media Start, Media Close | `a.media.episode` |
| Media feed type | The type of feed. | Media Start, Media Close | `a.media.feed` |
| Genre | The type or grouping of content as defined by the content producer. This dimension supports multiple values, delimited by commas. | Media Start, Media Close | `a.media.genre` |
| MVPD | The MVPD as provided by Adobe authentication. | Media Start, Media Close | `a.media.pass.mvpd` |
| Network | The network or channel name | Media Start, Media Close | `a.media.network` |
| Season | The season number that the show belongs to. | Media Start, Media Close | `a.media.season` |
| Show | The program or series name. | Media Start, Media Close | `a.media.show` |
| Show type | An integer that represents the type of content.<br>`0`: Full episode<br>`1`: Preview or trailer<br>`2`: Clip<br>`3`: Other | Media Start, Media Close | `a.media.type` |

{style="table-layout:auto"}
