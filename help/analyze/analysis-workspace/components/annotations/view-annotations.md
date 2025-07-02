---
title: View Annotations
description: How to view annotations in Analysis Workspace.
role: User, Admin
feature: Annotations
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
---
# View annotations

Annotations manifest slightly differently, depending on where they appear and whether they span a single day or a date range. 

## View annotations in Workspace

| Visualization<br/>Type | Description |
| --- | --- |
| **Line**<br/>**Single day** | When you select ![Annotate](/help/assets/icons/Annotate.svg) in a line visualization, you see a popup with the annotation details.<br/>![Annotation single day](assets/annotation-single-day.png)<br/>To edit edit the annotation in the [Annotation builder](create-annotations.md#annotation-builder) select ![Edit](/help/assets/icons/Edit.svg). To delete the annotation, select ![Delete](/help/assets/icons/Delete.svg). |
| **Line**<br/>**Date range** |  When you select ![AnnotateRange](/help/assets/icons/AnnotateRange.svg) you see a popup with the annotation details and a line at the bottom indicating the date range.<br/>![Annotation range](assets/annotation-range.png)To edit edit the annotation in the [Annotation builder](create-annotations.md#annotation-builder) select ![Edit](/help/assets/icons/Edit.svg). To delete the annotation, select ![Delete](/help/assets/icons/Delete.svg). |
| **Freeform table**| In a Freeform table, you can access all annotations from the annotations button at the top right of the visualization. Select ![Annotate](/help/assets/icons/Annotate.svg) to see a (scrolling list) of all annotations.<br/>![Annotations table](assets/annotations-table.png)<br/>For each annotation, you can select ![Edit](/help/assets/icons/Edit.svg) to edit the annotation in the [Annotation builder](create-annotations.md#annotation-builder) and ![Delete](/help/assets/icons/Delete.svg) to delete the annotation. |

{style="table-layout:auto"}

## View annotations in a PDF

When you download your project as a PDF, or send your project as a PDF, annotations are summarized in PDF in the Annotation summary section.

![Highlighted view of a .pdf file showing explanations of annotations.](assets/annotations-pdf.png)


<!--
# View annotations

Annotations manifest slightly differently, depending on whether they span a single day or a date range.

## View annotations in Line charts or Tables

| Date | Appearance |
| --- | --- |
| **Single day** |   ![](assets/single-day.png)<p>When you hover over the annotation, you can see its details, you can edit it by selecting the pen icon, or you can delete it:<p> ![](assets/hover.png) |
| **Date range** |  The icon changes and when you hover over it, the date range appears.<p>![](assets/multi-day.png)<p>When you select it in the line chart, the annotation metadata appear, and you can edit or delete it:![](assets/multi-hover.png)<p>In a table, an icon appears on every date in the date range.<p>![](assets/multi-day-table.png)|
| **Overlapping annotations** | On days that have more than one annotation tied to them, the icon appears in a grey color.<p>![](assets/grey.png)<p>When you hover over the grey icon, all overlapping annotations appear:<p>![](assets/overlap.png) |

{style="table-layout:auto"}

## View annotations in a .pdf file

Since you cannot hover over icons in a .pdf file, this file (after export) provides notes of explanations at the bottom of a panel. Here is an example:

![](assets/ann-pdf.png)

## View annotations with non-trended data

Sometimes annotation are shown with non-trended data, but tied to a specific dimension. In that case, they appear only in a summary annotation in the bottom right corner. Here is an example:

![](assets/non-date.png)

The summary chart appears in all visualization types in the corner, not just in non-trended freeform tables and summary numbers. It also appears in visualizations like [!UICONTROL Donut], [!UICONTROL Flow],[!UICONTROL Fallout],[!UICONTROL Cohort], and so on.

![](assets/ann-summary.png)

-->