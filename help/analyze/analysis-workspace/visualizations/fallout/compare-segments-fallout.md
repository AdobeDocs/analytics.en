---
description: You can create segments from a touchpoint, add segments as touchpoint, and compare key workflows across various segments in Analysis Workspace.
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: Apply segments in fallout analysis
feature: Visualizations
role: User, Admin
exl-id: 2177cd09-5a27-4295-8414-580cf53062cb
---
# Apply segments in fallout analysis

You can create segments from a touchpoint, add segments as touchpoint, and compare key workflows across various segments in Analysis Workspace.

>[!IMPORTANT]
>
>Segments used as checkpoints in Fallout must use a container that is at a lower level than the overall context of the Fallout visualization. With a visitor-context Fallout, segments used as checkpoints must be visit or hit-based segments. With a visit-context Fallout, segments used as checkpoint must be hit-based segments. If you use an invalid combination, the fallout will be 100%. We have added a warning to the Fallout visualization that will display when you add an incompatible segment as a touchpoint. Certain invalid segment container combinations will lead to invalid Fallout diagrams, such as:

* Using a visitor-based segment as a touchpoint inside a visitor-context Fallout visualization
* Using a visitor-based segment as a touchpoint inside a visit-context Fallout visualization
* Using a visit-based segment as a touchpoint inside a visit-context Fallout visualization

## Create a segment from a touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Create a segment from a specific touchpoint that you are especially interested in and that might be useful to apply to other reports. You do this by right-clicking the touchpoint and selecting **[!UICONTROL Create segment from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   The Segment Builder opens, pre-populated with the pre-built sequential segment that matches the touchpoint you selected:

   ![](assets/segment-builder.png)

1. Give the segment a title and description and save it.

   You can now use this segment in any report you wish.

## Add a segment as a touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

If you want to see, for example, how your US users trend and affect the fallout, just drag the US users segment into the fallout:

![](assets/segment-touchpoint.png)

Or you can create an AND touchpoint by dragging the US users segment onto another checkpoint.

## Compare segments in fallout {#section_E0B761A69B1545908B52E05379277B56}

You can compare an unlimited number of segments in the Fallout visualization.

Here is a video on comparing segments in fallout:

>[!VIDEO](https://video.tv.adobe.com/v/24046/?quality=12)

1. Select the segments you want to compare from the [!UICONTROL Segments] rail on the left. In our example, we have selected 2 segments: US Users and Non-US Users.
1. Drag them into the Segment drop zone at the top.

   ![](assets/segment-drop.png)

1. Optional: You can keep "All Visits" as the default container or delete it.

   ![](assets/seg-compare.png)

1. You can now compare the fallout across the two segments, such as where one segment is outperforming another, or other insights.
