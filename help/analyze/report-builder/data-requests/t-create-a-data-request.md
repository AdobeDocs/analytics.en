---
description: Steps to create a basic Report Builder data request.
title: Create a data request
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
feature: Report Builder
role: Business Practitioner, Administrator
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
---
# Create a Report Builder data request

Steps to create a basic data request.

1. In Excel, click **[!UICONTROL Create]**.
1. In the [!UICONTROL Request Wizard: Step 1] window, select a [report suite](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Optional) Select a segment to apply to the request. Once you have selected one or more segments, they will move to the top of the list.

   Report Builder uses segments in the same way Adobe Analytics uses them. See the [Analytics Segmentation Guide](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html). 1. (Optional) Select a [publishing list](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) to use for distribution.
1. Select a [report type](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Specify a [date range](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) and report [granularity](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).
1. Click **[!UICONTROL Next]**.
1. In the [Layout - Request Wizard Step 2](/help/analyze/report-builder/layout/layout.md) window, specify a layout:

   |  Element  | Description  |
   |---|---|
   |  Pivot Layout  | Provides a row, column, and metric grid for layout, similar to standard Excel tables. Using this layout, you can add breakdown requests within an original request.  |
   |  Custom Layout  | Provides most of the functionality of the [!UICONTROL Pivot Layout] but lets you choose where each item in the grid should be located in the spreadsheet. This layout provides the flexibility available in previous releases.  |

1. On the [!UICONTROL Metrics] tab, double-click (or drag) metrics in the tree to add them to the [!UICONTROL Metrics] grid.
1. On the [!UICONTROL Dimensions] tab, double-click (or drag) dimensions to the [!UICONTROL Row Labels] grid.

   The [dimensions](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/layout/filter-dimenson/filter-dimensions.html) available in Step 2 depend on the base report you selected in Step 1, and on the configuration of your report suite. The dimensions are items that correlate, sub-relate, or are a classification of the original report type metric you selected on the [!UICONTROL Request Wizard: Step 1] window. Adding more than one dimension in Step 2 is how you create a breakdown in your data request.

   See [Add Metrics and Dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) for more information.
