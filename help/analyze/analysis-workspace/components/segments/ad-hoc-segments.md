---
description: Use ad-hoc segments in Analysis Workspace.
title: Ad-hoc segments
feature: Segmentation
role: User, Admin
exl-id: 1c189abc-ab9f-413c-9be6-0d2fc457230e
---
# Ad-hoc project segments

Ad-hoc project segments allow you to drag and drop any component directly into the panel drop zone to create a segment. The segment becomes a [project-level segment](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?#what-are-project-only-segments%3F) local to the current project. 

Here is a video on creating ad-hoc project segments:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

1. Drop any component type (dimension, dimension item, event, metric, segment, segment template, date range) into the segment drop zone at the top of a panel. Component types are auto-converted into ad-hoc segments or [Quick segments](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html) if compatible.
   Here is an example of how to create a segment for the Twitter referring domain:

   ![](assets/ad-hoc1.png)

   Your panel automatically gets this segment applied and you can instantly see the results. 

1. You can add an unlimited number of segments to a panel.
1. If you decide that you want to save this segment, refer to the section below.

Keep in mind:

* You **cannot** drop the following component types into the segment zone: calculated metrics and dimensions/metrics from which you cannot build segments.
* For full dimensions and events, Analysis Workspace creates "exists" hit segments. Examples: `Hit where eVar1 exists` or `Hit where event1 exists`.
* If "unspecified" or "none" is dropped in the segment drop zone, it is automatically converted to a "does not exist" segment so that it is treated correctly in segmentation.

For a comparison of the different segments you can create and apply within a project, go [here](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

## Save ad-hoc  segments {#ad-hoc-save}

Ad-hoc segments can be made available to other projects by saving them.

1. Hover over the segment in the drop zone and click the "i" icon.
1. Click the edit pencil to go to the Segment Builder. 
2. Check **[!UICONTROL Make available to all projects and add to your component list]**. 
3. Click **[!UICONTROL SAVE]**. 

Once saved, the segment is available in your left rail component list and can be shared with other users from the Segment Manager.
