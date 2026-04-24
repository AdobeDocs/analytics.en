---
title: Streaming media services video metadata dimensions
description: Available dimensions when you enable [!UICONTROL Video Metadata] for a report suite.
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
TQID: https://experienceleague.adobe.com/Xgz-L8hPTQCfW6n-OEaw7u-8qNEGaXGVZTg3IBRbfKw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Streaming media services video metadata dimensions

*This page describes the available dimensions when you enable [!UICONTROL Video Metadata] for a report suite. See [Streaming media services video metadata metrics](../metrics/sm-video-metadata.md) for available metrics.*

Streaming media services ad dimensions provide supplemental reporting functionality to data collection through streaming media services collection libraries. Use of these dimensions require the **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Video Metadata]** under [Media reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), the following dimensions are available:

| Dimension name | Description | Sent with | Context data variable | XDM field |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Ad loads]** | The type of ad loaded. | | `a.media.adLoad` | `xdm.mediaCollection.`<br>`sessionDetails.adLoad` |
| **[!UICONTROL Day part]** | The time of the day when the content was broadcast or played. Any string value is supported. | Media Start, Media Close | `a.media.dayPart` | `xdm.mediaCollection.`<br>`sessionDetails.dayPart`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.dayPart` |
| **[!UICONTROL Episode]** | The episode number. | Media Start, Media Close | `a.media.episode` | `xdm.mediaCollection.`<br>`sessionDetails.episode`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.episode` |
| **[!UICONTROL Media feed type]** | The type of feed. | Media Start, Media Close | `a.media.feed` | `xdm.mediaCollection.`<br>`sessionDetails.feed`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.feed` |
| **[!UICONTROL Genre]** | The type or grouping of content as defined by the content producer. This dimension supports multiple values, delimited by commas. | Media Start, Media Close | `a.media.genre` | `xdm.mediaCollection.`<br>`sessionDetails.genre`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.genreList` |
| **[!UICONTROL MVPD]** | The MVPD as provided by Adobe authentication. | Media Start, Media Close | `a.media.pass.mvpd` | `xdm.mediaCollection.`<br>`sessionDetails.mvpd`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.mvpd` |
| **[!UICONTROL Network]** | The network or channel name. | Media Start, Media Close | `a.media.network` | `xdm.mediaCollection.`<br>`sessionDetails.network`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.network` |
| **[!UICONTROL Season]** | The season number that the show belongs to. | Media Start, Media Close | `a.media.season` | `xdm.mediaCollection.`<br>`sessionDetails.season`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.season` |
| **[!UICONTROL Show]** | The program or series name. | Media Start, Media Close | `a.media.show` | `xdm.mediaCollection.`<br>`sessionDetails.show`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.show` |
| **[!UICONTROL Show type]** | An integer that represents the type of content.<br>`0`: Full episode<br>`1`: Preview or trailer<br>`2`: Clip<br>`3`: Other | Media Start, Media Close | `a.media.type` | `xdm.mediaCollection.`<br>`sessionDetails.showType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.showType` |

