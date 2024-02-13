---
title: Calculated metrics totals
description: Learn about calculated metrics totals in Analysis Workspace
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
---
# Calculated metrics totals in Analysis Workspace

When you view data in Analysis Workspace, calculated metric totals are displayed in most cases. In some cases, providing a total is not possible, such as when the rows of the report are of mixed format (e.g. decimal and currency).

When totals are displayed, they are often calculated server-side, which means that the total de-duplicates metrics like visits or visitors. Under certain circumstances, calculated metrics are generated client-side by summing across rows of the table, which means the total does not de-duplicate metrics like visits or visitors. This occurs:

* When [static rows](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) are used in Freeform tables and the **[!UICONTROL Show as sum of current rows]** option (default) is selected.
* In the [Donut visualization](/help/analyze/analysis-workspace/visualizations/donut.md), so that numbers add up to 100%.

For more information on totals in Analysis Workspace, visit [Workspace totals](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html#static-row-total).
