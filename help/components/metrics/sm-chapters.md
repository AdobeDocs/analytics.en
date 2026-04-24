---
title: Streaming media services chapter metrics
description: Available metrics when you enable [!UICONTROL Media Chapters] for a report suite.
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
TQID: https://experienceleague.adobe.com/RE2A8dWALCgLL1J3t-kR62wOarFsFIGFgh9Pb-E2-Iw
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Streaming media services chapter metrics

*This page describes the available metrics when you enable [!UICONTROL Media Chapters] for a report suite. See [Streaming media services chapter dimensions](../dimensions/sm-chapters.md) for available dimensions.*

Streaming media services chapter metrics provide supplemental reporting functionality to data collection through streaming media services collection libraries. Use of these metrics require the **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Contact your Adobe Account Team for details.

When you enable **[!UICONTROL Media Chapters]** under [Media reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), the following metrics are available:

| Metric name | Description | Sent with | Context data variable | XDM field |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Chapter completes]** | A boolean that triggers when a chapter completes. | Chapter Close | `a.media.chapter.complete` | `xdm.mediaReporting.`<br>`chapterDetails.isCompleted` |
| **[!UICONTROL Chapter starts]** | A boolean that triggers when a chapter starts. | Chapter Start | `a.media.chapter.view` | `xdm.mediaReporting.`<br>`chapterDetails.isStarted` |
| **[!UICONTROL Chapter time spent]** | The amount of time spent on the chapter, in seconds. | Chapter Close | `a.media.chapter.timePlayed` | `xdm.mediaReporting.`<br>`chapterDetails.timePlayed` |
