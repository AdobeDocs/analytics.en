---
description: Use quick segments in Analysis Workspace.
title: Quick segments
feature: Workspace Basics
role: User, Admin
---

# Quick segments

You can create quick segments within a project to bypass the complexity of the full [segment builder](/help/components/segmentation/segmentation-workflow/seg-build.md). For a comparison of what quick segments can do vs. full-fledged component-list segments, go [here](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

>[!IMPORTANT]
> Quick segments are currently in limited testing and are not generally available yet.

## Create quick segments

1. In a Freeform table, click the filter+ icon in the panel header: 

   ![](assets/quick-seg1.png)

   Note that:

   - There is one segment container only that lets you include a dimension/metric/date range in (or exclude it from) the segment.
   - You can set the container to Hit, Visit, or Visitor level. Default is Hit.

1. Add a dimension/metric/date range in one of 3 ways:

   - Start typing and the [!UICONTROL Quick Segment builder] automatically finds the appropriate component.
   - Use the drop-down list to find the component.
   - Drag and drop components from the left rail.

1. Specify the first rule, such as `Page equals workspace`. You can have up to three rules in a segment definitions. Just click the "+" sign to add another rule. You can add "AND" or "OR" qualifiers to the rules, but you cannot mix "AND" and "OR" in a single segment definition. 

   Here is an example of a segment that combines dimensions and metrics:

   ![](assets/quick-seg2.png)

1. Click **[!UICONTROL Apply]** to apply this segment to the panel. 
   The segment appears at the top. Notice its grey sidebar, as opposed to the blue sidebar for component-level segments in the segment library on the left.

   ![](assets/quick-seg3.png)

## Edit quick segments

1. Hover over the quick segment and select the pencil icon.
1. Edit the segment definition or the segment name.

## Save quick segments

You can choose to save quick segments by following these steps.

>[!IMPORTANT]
>Once you save or apply the segment, you can no longer edit it in the Quick Segment Builder, only in the regular Segment Builder.

1. Hover over the quick segment and select the info ("i") icon.
1. Select **[!UICONTROL Save segment]**

   ![](assets/save-quick-seg.png)

1. Leave the name as is or rename the segment.

   Go back to Workspace and notice how the segment now has a blue sidebar. This indicates it can no longer be edited/opened in the Quick Segment Builder. And by saving it, it becomes part of the component list.

   ![](assets/quick-seg4.png)

After you have applied the segment, you can choose to add it to your segment component list and make it available to all your projects. 

1. Hover over the saved segment and select the pencil icon.

1. At the top of the Segment Builder, notice this dialog:

   ![](assets/project-only.png)

1. Select the checkbox next to **[!UICONTROL Make this segment available to all your projects and add it to your component list.]**
1. Click **[!UICONTROL Save]**.
1. The segment now appears in your segment component list for all your projects.
1. You can also [share the segment](/help/components/segmentation/segmentation-workflow/t-seg-share.md) with other people in your organization.

## What are project-only segments?

Project-only segments are either quick segments or ad-hoc Workspace project segments. When editing/opening them in the segment builder then the project-only box will show up. If they APPLY a quick segment in the builder but don’t check the make available box, then it is still a project-only segment but it can no longer be opened in the QS builder. If they check the box and SAVE it is now a component-list segment. 