---
description: List of known limitations in Adobe Analysis Workspace and its related components
title: Known limitations in Analysis Workspace
feature: Workspace Basics
role: Business Practitioner, Administrator
exl-id: 520e970b-1387-4f70-985b-bfe397f4a21b
---
# Known limitations in Analysis Workspace 

Here is a list of known limitations in Analysis Workspace and its related components:

## Tables

* Date comparison columns cannot be added when either date ranges or metrics are used as rows of a table.
* Create metric from selection is disabled when segments are used as rows of a table. Additionally, Create metric from selection should not be applied to date-aligned columns.
* Conditional formatting for breakdown rows cannot use custom ranges.
* Table total rows cannot be trended when Calculate totals by summing the row values setting is applied (typically used with Static row items).
* [!UICONTROL Contribution Analysis] can be run at the [!UICONTROL daily] granularity _only_. It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualizations

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flow]: Entry/Exit dimensions, e.g. [!UICONTROL Entry page], cannot be used in Flow.
* [!UICONTROL Cohort]: Non-integers cannot be used as Cohort criteria.

## Panels

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## Components > Segments

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Adhoc segments created in the [panel dropzone](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html) will not appear in the left rail of Workspace or the Segment component manager, unless they are made public. This can be done by editing the segment and selecting **[!UICONTROL Make this segment public]**.

## Components > Calculated Metrics

* Calculated metrics cannot be used in certain visualizations. See 'Visualizations' above.
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). For example, [!UICONTROL IP Address].

## Components > Date Ranges

* Custom date ranges do not support [!UICONTROL This day last year], [!UICONTROL This day last month], etc.

## Components > Virtual Reports Suites

* When report time processing is enabled, certain components are not supported. For a full list, see [Report Time Processing](/help/components/vrs/vrs-report-time-processing.md).

## Components > All components > Report settings

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. Analysis Workspace uses only the [!UICONTROL Language/Currency/Encoding] settings at the bottom: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], and [!UICONTROL CSV Separator Character].

## Attribution IQ

* A subset of metrics is not supported in [!UICONTROL Attribution IQ]. For a full list, see the [Attribution IQ FAQ](../attribution/faq.md).
