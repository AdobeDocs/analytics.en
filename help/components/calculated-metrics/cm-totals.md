---
title: Calculated metrics totals
description: Learn about calculated metrics totals in Analysis Workspace
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
TQID: https://experienceleague.adobe.com/3UJF1Hl3nLqjYAiQuvcE4Jpq26MaTgeba5BmnVfvEps
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
  - id: e318d41c-1d01-4c1e-9b18-1f61d435ceee
    internal-label: Freeform tables
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Calculated metrics totals

When you view data in Analysis Workspace, calculated metric totals are displayed in most cases. In some cases, providing a total is not possible, such as when the rows of the report are of mixed format (e.g. decimal and currency).

When totals are displayed, they are often calculated server-side, which means that the total de-duplicates metrics like visits or visitors. Under certain circumstances, calculated metrics are generated client-side by summing across rows of the table, which means the total does not de-duplicate metrics like visits or visitors. This occurs:

* When [static rows](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) are used in Freeform tables and the **[!UICONTROL Show as sum of current rows]** option (default) is selected.
* In the [Donut visualization](/help/analyze/analysis-workspace/visualizations/donut.md), so that numbers add up to 100%.

For more information on totals in Analysis Workspace, visit [Workspace totals](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md#static-row-total).
