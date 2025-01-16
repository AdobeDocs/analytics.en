---
description: Use the Summary Number and Change visualizations to display important data points in a project.
title: Summary Number and Summary Change
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
---
# [!UICONTROL Summary Number] and [!UICONTROL Summary Change]

*This article documents the Summary number and Summary change visualization in **Adobe Analytics**.<br/>See [Summary number and Summary change](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change) for the **Customer Journey Analytics** version of this article.*

Here is a video on these two visualizations:

>[!VIDEO](https://video.tv.adobe.com/v/335564/?quality=12)

## [!UICONTROL Summary Number] visualization {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Summary number"
>abstract="Create a visualization that shows totals and subtotals."

<!-- markdownlint-enable MD034 -->

Use the [!UICONTROL Summary Number] visualization to highlight a large number that is important in a project. This visualization behaves in the following ways:

* Selects the total of the column if no cell is selected.
* If a single cell is selected, it shows the summary for that cell.
* If more than one cell is selected, it shows the first cell selected.
* If the column is selected, it picks the first cell value in the column.

Click the **Visualization settings** gear in to the top right to configure the Summary Number settings: 

| Setting | Definition |
|--- |--- |
| [!UICONTROL Percentages] | Display percentages instead of raw numbers.|
| [!UICONTROL Legend visible] | Display information about the metric displayed.|
| [!UICONTROL Abbreviate value] | Choose to abbreviate values and show up to 3 decimal places.|
| [!UICONTROL Summarize value by] | Choose to display the max, min, mean, median, or sum for a selection of data.|

## [!UICONTROL Summary Change] visualization {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Summary change"
>abstract="Create a visualization that shows the delta (change) between two numbers"

<!-- markdownlint-enable MD034 -->

Use the [!UICONTROL Summary Change] visualization to show the delta (change) between two numbers. The green and red color of the [!UICONTROL Summary Change] can be controlled through [custom event polarity](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.

This visualization behaves in the following ways:

* If no cell is selected, it compares the first two cell values in the column.
* If one cell is selected, it shows 0, because it compares the cell value to itself.
* If two cells are selected, the first selected cell is taken as numerator and the second as denominator.
* If more than two cells are selected, it only considers the first two for comparison.
* If a range of cells is selected, it compares the first to the last cells selected in the range.
* If the column is selected, it compares the first value to itself, which shows a change of 0.


![](assets/summary-change.png)


Click the **Visualization settings** gear in to the top right to configure the Summary Change settings: 

| Setting | Definition |
| --- | --- |
| [!UICONTROL Percentages] | Display percentages instead of raw numbers. |
| [!UICONTROL Legend visible] | Display information about the metric displayed. |
| [!UICONTROL Show Percent Change] | Shows the percent change between the 2 numbers. |
| [!UICONTROL Show Raw Difference] | Shows the raw difference between the 2 numbers. You can also abbreviate values and show up to 3 decimal places with this option. |
