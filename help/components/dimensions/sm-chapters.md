---
title: Streaming Media chapter dimensions
description: Available dimensions when you enable [!UICONTROL Media Chapters] for a report suite.
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
TQID: https://experienceleague.adobe.com/AfI1gvM3quhjC1zV6oRKx86vS-aLDIRNtuw1vEhuK4A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Streaming media services chapter dimensions

*This page describes the available dimensions when you enable [!UICONTROL Media Chapters] for a report suite. See [Streaming media services chapter metrics](../metrics/sm-chapters.md) for available metrics.*

Streaming media services chapter dimensions provide supplemental reporting functionality to data collection through streaming media services libraries. Use of these dimensions require the **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Media Chapters]** under [Media reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), the following dimension is available:

| Dimension name | Description | Sent with | Context data variable | XDM field |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Chapter]** | The automatically generated chapter ID. | Chapter Close | `a.media.chapter.name` | `xdm.mediaReporting.`<br>`chapterDetails.ID` |

In addition to the above dimensions, Adobe automatically creates the following classification dimensions. You must upload classification data to view reports that use these dimensions.

| Classification name | Parent dimension | Description |
| --- | --- | --- |
| **[!UICONTROL Originator]** | [[!UICONTROL Content]](sm-core.md) | The creator of the content. |
| **[!UICONTROL Chapter length]** | [!UICONTROL Chapter] | The length of the chapter, in seconds. |
| **[!UICONTROL Chapter name]** | [!UICONTROL Chapter] | The friendly name of the chapter. |
| **[!UICONTROL Chapter offset]** | [!UICONTROL Chapter] | The offset of the chapter inside the content from the start, in seconds. |
| **[!UICONTROL Chapter position]** | [!UICONTROL Chapter] | The index position of the chapter in the content. |
