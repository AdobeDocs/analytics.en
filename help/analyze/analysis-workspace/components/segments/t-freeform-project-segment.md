---
description: Use segments in Analysis Workspace.
title: Segments
feature: Segmentation
role: User, Admin
exl-id: 67112e13-4d0a-4d77-be50-496c3d28779c
---

# Segments {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

You can create different types of segments in Workspace, depending on how complex they need to be, whether they should apply to this project only, etc. Here is a summary of segment types:

| Segment type | Created where? | Applicable where? | When to use |
| --- | --- | --- | --- |
| Component-list segment | Click +, which takes you to the [Segment Builder](/help/components/segmentation/segmentation-workflow/seg-build.md) | All your Workspace projects | For more complex segments, sequential segments |
| Quick segment | [Quick segment builder](/help/analyze/analysis-workspace/components/segments/quick-segments.md) | Project only, but can save and add to your segment list. | Can be used for ad hoc single-rule segments (with drag-and-drop), or to add/edit multiple rules (by clicking the Segment icon) | 
| Calculated metrics-based segment | [Calculated metric builder](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html) | To individual calculated metric | Apply segment/s within your metric definition |
| VRS-based segment | [Virtual report suite builder](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) | To individual virtual report suite | Apply segment/s within your VRS definition |

## Videos

Using segments in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23977/?quality=12)

Finding and creating segments:

>[!VIDEO](https://video.tv.adobe.com/v/334092/?quality=12)

Rolling date ranges in segments:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Create segments {#section_693CFADA668B4542B982446C2B4CF0F5}

You can create different types of segments in Analysis Workspace:

* [Quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md)
* Regular component-list segments that you create in the Segment Builder and that end up in the segment library (see below)

### Create component-list segments {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

The segment rail under the Components menu shows 
* Segments you or your company created
* Segment templates, as signified by the Adobe icon:

![](assets/segment_icons.png)

To create a segment of this type, you have 2 options. Both of them take you to the [Segment Builder](/help/components/segmentation/segmentation-workflow/seg-build.md) in Adobe Analytics, where you can find further instructions.

* In the left rail, click the plus sign (+) next to [!UICONTROL Segments]:

![](assets/create-seg.png)

or 

* Go to [!UICONTROL Components] > [!UICONTROL Segments], then click [!UICONTROL + Add].


### Other methods for applying segments {#section_10FF2E309BA84618990EA5B473015894}

>[!VIDEO](https://video.tv.adobe.com/v/30994/?quality=12)

Several other methods exist for applying segments to a freeform project.

| Action | Description |
|--- |--- |
| Create segment from selection | Create an inline segment. This segment applies only to the open project and is not saved as an Analytics segment. 1. Select rows.  2. Right-click the selection.  3. Click *Create segment from selection*. |
| Components > New Segment | Displays the Segment Builder. See [Segment Builder](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html) for more information about segmentation. |
| Share > Share Project or Share > Curate Project Data | In [Curate and Share](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), learn how segments that you apply to the project are available in shared analysis for the recipient. |
| Use Segments as Dimensions | Video: [Using Segments as Dimensions in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-as-dimensions-in-analysis-workspace.html) |

## Segment IQ

Segment IQ (also known as Segment Comparison) comprises the following features:

* [Segment comparison panel:](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) The core feature in Segment IQ. Drag two segments into the panel, and view a comprehensive report that shows statistically significant differences and overlap between the two audiences.
* [Comparing segments in fallout:](/help/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md) See how different audiences compare to each other in context of a fallout visualization.

## More info

For an in-depth discussion of segmentation in Adobe Analytics, go [here](/help/components/segmentation/seg-overview.md).
