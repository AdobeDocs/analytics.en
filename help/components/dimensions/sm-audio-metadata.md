---
title: Streaming media services audio metadata dimensions
description: Available dimensions when you enable [!UICONTROL Audio Metadata] for a report suite.
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
---
# Streaming media services audio metadata dimensions

Streaming media services ad dimensions provide supplemental reporting functionality to data collection through Streaming media services libraries. Use of these dimensions require the **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Audio Metadata]** under [Media reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), the following dimensions are available:

| Dimension name | Description | Sent with | Context data variable | XDM field |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Album]** | The name of the album. | Media Start, Media Close | `a.media.album` | `xdm.mediaCollection.`<br>`sessionDetails.album`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.album` |
| **[!UICONTROL Artist]** | The name of the artist. | Media Start, Media Close | `a.media.artist` | `xdm.mediaCollection.`<br>`sessionDetails.artist`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.artist` |
| **[!UICONTROL Author]** | The name of the audio book author. | Media Start, Media Close | `a.media.author` | `xdm.mediaCollection.`<br>`sessionDetails.author`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.author` |
| **[!UICONTROL Label]** | The name of the record label. | Media Start, Media Close | `a.media.label` | `xdm.mediaCollection.`<br>`sessionDetails.label`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.label` |
| **[!UICONTROL Publisher]** | The name of the audio content publisher. | Media Start, Media Close | `a.media.publisher` | `xdm.mediaCollection.`<br>`sessionDetails.publisher`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.publisher` |
| **[!UICONTROL Station]** | The name or ID of the radio station. | Media Start, Media Close | `a.media.station` | `xdm.mediaCollection.`<br>`sessionDetails.station`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.station` |
