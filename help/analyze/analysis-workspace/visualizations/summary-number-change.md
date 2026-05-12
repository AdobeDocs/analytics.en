---
description: Use the Summary Number and Change visualizations to display important data points in a project.
title: Summary Number And Summary Change
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
TQID: https://experienceleague.adobe.com/d8sqa6xvvXnh4qJlJua3bTCHsmm7yjcVWbMabTcJdrI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Summary number and change

>[!BEGINSHADEBOX]

_This article documents the Summary number and Summary change visualizations in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe  Analytics**._<br/>_See [Summary number and Summary change](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change) for the_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** version of this article._

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Summary number and Summary change visualization](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/visualizations/summary-number-and-summary-change-visualizations-2021){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Summary number {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Summary number"
>abstract="Create a visualization that shows totals and subtotals."

<!-- markdownlint-enable MD034 -->

Use the ![Summarize](/help/assets/icons/123.svg) **[!UICONTROL Summary number]** visualization to highlight a large number that is important in a project. This visualization behaves in the following ways, using the associated data source:

* Selects the total of the column if no cell is selected.
* If a single cell is selected, it shows the summary for that cell.
* If more than one cell is selected, it shows the first cell selected.
* If the column is selected, it picks the first cell value in the column.

![Summary number visualization](asses/../assets/summary-number.png)

As part of the visualization settings, specific Summary number options are available.

| Option | Definition |
|--- |--- |
| **[!UICONTROL Abbreviate value]** | Select **[!UICONTROL Abbreviate value]** to abbreviate intelligently the number value. When selected, enter a number to define the amount of abbreviation. For example:<br/><table><tr><td>**Original value**</td><td>**Abbreviation value**</td><td>**Result**</td></tr><tr><td>$12,011,141.25</td><td>Not selected</td><td  align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>Selected, set to `0`</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td> Selected, set to `1`</td><td  align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>Selected, set to `2`</td><td align="right">$12.01M</td></tr><tr><td>$12,011,141.25</td><td>Selected, set to `3`</td><td align="right">$12.011M</td></tr></table> |
| **[!UICONTROL Summarize value by]** | Choose to display the max, min, mean, median, or sum for a selection of data. |

## Summary change {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Summary change"
>abstract="Create a visualization that shows the delta (change) between two numbers"

<!-- markdownlint-enable MD034 -->


Use the ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL Summary Change]** visualization to show the delta (change) between two numbers. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](/help/admin/tools/success-events/success-event.md) or a calculated metric's [Show Upward Trend As](/help/components/calculated-metrics/workflow/cm-build-metrics.md) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md.md) or a calculated metric's [Show Upward Trend As](/help/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.md) option.
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
