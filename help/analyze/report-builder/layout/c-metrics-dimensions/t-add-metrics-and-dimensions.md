---
description: Steps to add metrics and dimensions to a request.
title: Add metrics and dimensions
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
feature: Report Builder
role: User, Admin
exl-id: d4e36b69-b5aa-43e5-b394-3b6d93143f15
---
# Add metrics and dimensions

Steps to add metrics and dimensions to a request.

1. [Create the data request](/help/analyze/report-builder/data-requests/data-requests.md) on the [!UICONTROL Request Wizard: Step 1], then click **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2], double-click metrics, or drag them to the desired position.

   ![Step Info](assets/adding_metrics.png)

    When you add metrics, they are not removed from the [!UICONTROL Metrics] tab, because you can display metrics multiple times within a request. For example, you can display the metric subtotal in addition to each value. However, the list of available metrics changes each time you add or remove a dimension.

    You can add only metrics to the [!UICONTROL Metrics] layout section. Metrics are added to the [!UICONTROL Column Label] layout as a [!UICONTROL Metric Header]. If you move a [!UICONTROL Metric Header] from [!UICONTROL Column Layout] to [!UICONTROL Row Layout], it is displayed there and is used as a metric as a breakdown.

    Note that a Search bar is shown on the Metrics tab, just above the Metric list.

    ![](assets/search_bar_metric.png)

    Keep this in mind:

    * As you enter a search term, the list will automatically update to only display the metrics whose label matches the search term.
    * The match is case insensitive, and equivalent to a "contains" search.
    * Full-word searches, or other special search flag (starts with, ends with, AND, OR, etc.) are not supported.

       The Search term will be cleared if you exit the Request Wizard (i.e., click Finish or Cancel), or go back to Request Wizard Step 1, or change the Metric category.

       The Search term will not be cleared in the following cases:

    * You drag and drop (or double click) one of the metric item from the list so it gets added to the Pivot Layout/Custom Layout Metrics Panel.
    * You remove a metric item(s) from the Pivot Layout/Custom Layout Metric Panel.
    * You click the Dimension tab, then return to the Metric tab.
    * You invoke other sub forms (modal or modeless) that upon exit will return to the Request Wizard Step 2. Examples of these forms are

        * Dimension Filter Forms 
        * Date Range Formatting Forms 
        * Format Options Form 
        * Prepend-Postpend Text Form 
        * Output Range Location Form

1. (Optional) To sort a request by metric, just click the metric label.
1. Add dimensions the same way you add metrics.

On the [!UICONTROL Dimensions] tab, the system displays dimensions that break down or are a classification of any base report you select on Step 1, and on the configuration of the report suite. When you drop a dimension to the layout grids, it is removed from the tree view and recalculates the list of remaining dimensions available.

The [!UICONTROL Date] dimension is added automatically. Available date dimensions change depending on the selected granularity from the [!UICONTROL Request Wizard: Step 1]. (Valid values are:

    * Hour 
    * Day 
    * Week 
    * Month 
    * Year 
    * Date range (when no granularity is specified)

1. Modify metrics and dimensions by configuring [format options](/help/analyze/report-builder/layout/t-format-display-headers.md) and filters.
1. Click **[!UICONTROL Finish]**.
In the following example, dimensions relate to the [!UICONTROL Page] metric. Here, the [!UICONTROL Referring Domain] dimension creates a breakdown report between [!UICONTROL Page] and [!UICONTROL Referring Domain]. The [!UICONTROL Dimension] tab is updated with only dimensions that you can add to a breakdown report.

![](assets/page_pageview_02.png)
