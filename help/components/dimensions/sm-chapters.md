---
title: Streaming Media chapter dimensions
description: Available dimensions when you enable [!UICONTROL Media Chapters] for a report suite.
feature: Dimensions
---
# Streaming Media chapter dimensions

Streaming Media chapter dimensions provide supplemental reporting functionality to data collection through streaming media collection libraries. Use of these dimensions require the **[!UICONTROL Adobe Streaming Media Collection Add-on]**. Contact your Adobe Account Team for details.

| Dimension name | Description | Sent with | Context data variable |
| --- | --- | --- | --- |
| Chapter | The automatically generated chapter ID. | Chapter Close | `a.media.chapter.name` |

{style="table-layout:auto"}

In addition to the above dimensions, Adobe automatically creates the following classification dimensions. You must upload classification data to view reports that use these dimensions.

| Classification name | Parent dimension | Description |
| --- | --- | --- |
| Originator | [Content](sm-core.md) | The creator of the content. |
| Chapter length | Chapter | The length of the chapter, in seconds. |
| Chapter name | Chapter | The friendly name of the chapter. |
| Chapter offset | Chapter | The offset of the chapter inside the content from the start, in seconds. |
| Chapter position | Chapter | The index position of the chapter in the content. |

{style="table-layout:auto"}
