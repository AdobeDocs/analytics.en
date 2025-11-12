---
title: Streaming media services ad dimensions
description: Available dimensions when you enable [!UICONTROL Media Ads] for a report suite.
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
---
# Streaming media services ad dimensions

*This page describes the available dimensions when you enable [!UICONTROL Media Ads] for a report suite. See [Streaming Media ad metrics](../metrics/sm-ads.md) for available metrics.*

Streaming media services ad dimensions provide supplemental reporting functionality to data collection through Streaming media services libraries. Use of these dimensions require the **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Media Ads]** under [Media reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), the following dimensions are available:

| Dimension name | Description | Sent with | Context data variable | XDM field |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Ad]** | The unique identifier for the ad. | Ad Start, Ad Close | `a.media.ad.`<br>`name` | `xdm.mediaCollection.`<br>`advertisingDetails.name`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.name` |
| **[!UICONTROL Ad name (variable)]** | The friendly name of the ad. A classification dimension named '[!UICONTROL Ad name]' is also available, which provides a similar purpose. This dimension and the classification are treated as two distinct dimensions. | Ad Start, Ad Close | `a.media.ad.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`advertisingDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.friendlyName` |
| **[!UICONTROL Ad player name]** | The name of the player that renders the ad. | Ad Start, Ad Close | `a.media.ad.`<br>`playerName` | `xdm.mediaCollection.`<br>`advertisingDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.playerName` |
| **[!UICONTROL Ad length (variable)]** | The length of the video ad, in seconds. | Ad Start, Ad Close | `a.media.ad.`<br>`length` | `xdm.mediaCollection.`<br>`advertisingDetails.length`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.length` |
| **[!UICONTROL Ad pod]** | The unique identifier for the ad pod. | Ad Start, Ad Close | `a.media.ad.`<br>`pod` | |
| **[!UICONTROL Ad in pod position]** | The index position of the ad inside the parent ad break (0-indexed). | Ad Start, Ad Close | `a.media.ad.`<br>`podPosition` | `xdm.mediaCollection.`<br>`advertisingDetails.podPosition`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.podPosition` |
| **[!UICONTROL Advertiser]** | The company or brand featured in the ad. | Ad Start, Ad Close | `a.media.ad.`<br>`advertiser` | `xdm.mediaCollection.`<br>`advertisingDetails.advertiser`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.advertiser` |
| **[!UICONTROL Campaign ID]** | The ID of the ad campaign | Ad Start, Ad Close | `a.media.ad.`<br>`campaign` | `xdm.mediaCollection.`<br>`advertisingDetails.campaignID`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.campaignID` |

In addition to the above dimensions, Adobe automatically creates the following classification dimensions. You must upload classification data to view reports that use these dimensions.

| Classification name | Parent dimension | Description |
| --- | --- | --- |
| **[!UICONTROL Asset ID]** | [[!UICONTROL Content]](sm-core.md) | The unique identifier for the content of the media asset. Examples include the TV series episode identifier, movie asset identifier, or live event identifier. These IDs are typically derived from metadata authorities such as EIDR, TMS/Gracenote, Rovi, or from other proprietary or in-house systems. |
| **[!UICONTROL Content rating]** | [[!UICONTROL Content]](sm-core.md) | The rating as defined by TV parental guidelines. |
| **[!UICONTROL First air date]** | [[!UICONTROL Content]](sm-core.md) | The date when the content first aired on television. Since this classification dimension is a string, any date format is allowed. Adobe recommends using a consistent date format, such as `YYYY-MM-DD`. |
| **[!UICONTROL First digital date]** | [[!UICONTROL Content]](sm-core.md) | The date when the content first aired on any digital channel or platform. Since this classification dimension is a string, any date format is allowed. Adobe recommends using a consistent date format, such as `YYYY-MM-DD`. |
| **[!UICONTROL Ad length]** | [!UICONTROL Ad] | The length of the video ad, in seconds. |
| **[!UICONTROL Ad name]** | [!UICONTROL Ad] | The friendly name of the ad. It is the classification equivalent of '[!UICONTROL Ad name (variable)]'. |
| **[!UICONTROL Creative ID]** | [!UICONTROL Ad] | The ID of the ad creative. |
| **[!UICONTROL Pod name]** | [!UICONTROL Ad pod] | The friendly name of the ad pod. |
| **[!UICONTROL Pod position]** | [!UICONTROL Ad pod] | The offset of the ad break inside the content, in seconds. |
