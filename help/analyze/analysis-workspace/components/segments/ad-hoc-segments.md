---
description: Use ad-hoc segments in Analysis Workspace.
title: Ad-hoc segments
feature: Workspace Basics
role: User, Admin
---

# Ad-hoc segments

Here is a video on creating ad hoc segments:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

You can create ad-hoc segments if you want to quickly explore how a segment might affect your project. Think of these segments as temporary, project-level segments. They will typically not be part of your segment "library" like component segments in the left rail. However, you can add them to your library, as shown in step ? below.

1. Drop any component type (dimension, dimension item, event, metric, segment, segment template, date range) into the segment drop zone at the top of a panel. Component types are auto-converted into segments.
2. 

Keep in mind that:

* You **cannot** drop the following component types into the segment zone: calculated metrics and dimensions/metrics from which you cannot build segments.
* For full dimensions and events, Analysis Workspace creates "exists" hit segments. Examples: `Hit where eVar1 exists` or `Hit where event1 exists`.
* If "unspecified" or "none" is dropped in the segment drop zone, it is automatically converted to a "does not exist" segment so that it is treated correctly in segmentation.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Segments created this way are internal to the project.

## Make ad-hoc segments public

You can choose to make these segments public (global) by following these steps:

1. Hover over the segment in the drop zone and click the "i" icon.
1. In the information panel that displays, click **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)