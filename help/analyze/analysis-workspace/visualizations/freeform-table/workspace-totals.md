---
description: Learn how totals in freeform tables in Analysis Workspace are calculated.
title: Totals
feature: Freeform Tables
role: User, Admin
exl-id: 883c3e44-4139-46a1-a261-e11841312465
TQID: https://experienceleague.adobe.com/wxOqh9uQC1oDpjGjZwp-A4Ir0PfH1cH8y5l9IYM-3io
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
  - id: e318d41c-1d01-4c1e-9b18-1f61d435ceee
    internal-label: Freeform tables
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Totals {#workspace-totals}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="Grand Total"
>abstract="Grand total is not supported for tables or breakdowns with static rows."

In Freeform tables, a total row appears at each breakdown level and can show two totals:

![Freeform Table highlighting the grand total and the table total.](assets/total-row.png)

* **[!UICONTROL Table total]** ➊ - This total is typically equal to or a subset of the [!UICONTROL Grand total]. The total reflects any table filters applied within the freeform table, including the [!UICONTROL Include None] option.
* **[!UICONTROL Grand total]** (**[!UICONTROL out of]** *number*) ➋ - This total represents all events that have been collected. When a filter is applied either at the panel level or within the freeform table, this total adjusts to reflect all events that match the filter criteria.




## Display totals

Under ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Column settings]**, there are options to **[!UICONTROL Show totals]** and **[!UICONTROL Show grand total]**. If these settings are unchecked, totals are removed from the table, which may be desired in cases where totals don't make sense.


In a freeform table that contains [static rows](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md), totals behave differently. And are controlled using ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Row Settings]**.

| Option | Description |
|---|---|
| **[!UICONTROL Show sum of current rows as the total]** | Show a client-side sum of the rows in the table. This total does **not** de-duplicate metrics like sessions or persons. |
| **[!UICONTROL Show grand total]** | Show a server-side sum. This total de-duplicate metrics like sessions or persons. |

See [Dynamic vs static dimension items in freeform tables](column-row-settings/manual-vs-dynamic-rows.md).


## Frequently asked questions

|Questions|Answer|
|---|---|
| Which *total* are the gray column percentages based on? | This *total* depends on the **[!UICONTROL Percentages]** setting selection under **[!UICONTROL Row Settings]**:<ul><li>Calculate percentages by column - This setting is the default. Percentages are based on the Table total.</li><li>Calculate percentages by row - Percentages are based on the Grand total.</li></ul>|
|How does the **[!UICONTROL Include Unspecified (None)]** setting impact totals?|If the Include Unspecified (None) setting is unchecked, the None/Unspecified row will be removed from the table, the Table Total, and will carry through to any calculated metrics that use ['Total' metric types](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md).|
|When custom table filters are applied to a freeform table, do all of my calculated metrics and conditional formatting account for the filter?|Not currently. **[!UICONTROL Include Ubnspeficied (None) ]** is account for, but custom table filters do not impact the following:<ul><li>The column max / min range that conditional formatting uses looks across all data.</li><li>Calculated metrics that leverage **[!UICONTROL Grand total]** metric types.</li><li>Calculated metrics with functions that calculate across rows in a freeform table: Column Sum, Column max, Column min, Count, Mean, Median, Percentile, Quartile, Row Count, Standard Deviation, Variance, Cumulative, Cumulative Average, Regression variants, T-Score, T-Test, Z-Score, and Z-Test.</li></ul>|
|In Calculated Metrics, what does the **[!UICONTROL Grand total]** metric type reflect?|**[!UICONTROL Grand total]** continues to refer to the **[!UICONTROL Grand total]**, and does not reflect filters applied to a table or the **[!UICONTROL Table total]**.|
|What total is shown when data is either copied and pasted from a freeform table or downloaded via CSV?|The total row reflects the **[!UICONTROL Table total]** only and respects the column **[!UICONTROL Show totals]** setting.|
