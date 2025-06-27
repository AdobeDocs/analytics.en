---
description: Use the Summary Number and Change visualizations to display important data points in a project.
title: Summary Number And Summary Change
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
---
# [!UICONTROL Summary number] and [!UICONTROL Summary change]

_This article documents the Summary number and Summary change visualizations in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_See [Summary number and Summary change](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change)  for the_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** version of this article._


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Summary number and Summary change visualization](https://video.tv.adobe.com/v/335564/?quality=12){target=&#34;_blank&#34;} for a demo video.

>[!ENDSHADEBOX]


## [!UICONTROL Summary Number] visualization {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Summary number"
>abstract="Create a visualization that shows totals and subtotals."

<!-- markdownlint-enable MD034 -->


Use the ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL Summary Change]** visualization to show the delta (change) between two numbers. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

This visualization behaves in the following ways:

* If no cell is selected, it compares the first two cell values in the column.
* If one cell is selected, it shows 0, because it compares the cell value to itself.
* If two cells are selected, the first selected cell is taken as numerator and the second as denominator.
* If more than two cells are selected, it only considers the first two for comparison.
* If a range of cells is selected, it compares the first to the last cells selected in the range.
* If the column is selected, it compares the first value to itself, which shows a change of 0.


![Summary change visualization showing the delta between two numbers.s](assets/summary-change.png)


As part of the visualization settings, specific **[!UICONTROL Summary change options]** are available.

| Option | Definition |
|--- |--- |
| **[!UICONTROL Show percent change]**| Show the percent change between the 2 numbers.|
| **[!UICONTROL Show raw difference]** | Show the raw difference between the 2 numbers. You can also abbreviate values and show up to 3 decimal places with this option.|
| **[!UICONTROL Abbreviate value]** | Select **[!UICONTROL Abbreviate value]** to abbreviate intelligently the changed value. When selected, enter a number to define the amount of abbreviation. For example:<br/><table><tr><td>**Original value**</td><td>**Abbreviation value**</td><td>**Result**</td></tr><tr><td>$12,011,141.25</td><td>Not selected</td><td  align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>Selected, set to `0`</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td> Selected, set to `1`</td><td  align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>Selected, set to `2`</td><td align="right">$12.01M</td></tr><tr><td>$12,011,141.25</td><td>Selected, set to `3`</td><td align="right">$12.011M</td></tr></table> |

>[!MORELIKETHIS]
>
>[Add a visualization to a panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualization settings](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Visualization context menu](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
