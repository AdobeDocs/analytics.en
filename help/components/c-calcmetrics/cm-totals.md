---
title: Calculated metrics totals
description: Learn how calculated metrics totals differ in Analytics tools
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
---
# Calculated metrics totals

How calculated metric totals are displayed differs between [!DNL Reports & Analytics] and [!DNL Analysis Workspace]. This section explains the differences.

## Calculated metrics totals in [!DNL Reports & Analytics]

When you view reports in [!DNL Reports & Analytics], calculated metrics always display `n/a` under the total. Since all calculated metrics are user-defined, there are many circumstances where this total doesn't make sense. Consider the following example:

Your organization has created the calculated metric `orders` / `visits` to determine the percentage of visits that purchased something on your site. If you brought this metric into a products report, several products are attributed to a single order. And, several products are attributed to a single visit. If a calculated metric total was included in this report, the following questions arise:

|Question| Answer|
|---|---|
|Does summing the line items make sense?|It doesn't, since multiple products can be included in a single order, and multiple products can be included in a single visit. If the line items were aggregated, total orders and total visits would not match the actual total orders and total visits.|
|Does taking total orders and total visits make sense?|It doesn't, as the total doesn't match the sum of the individual line items. In addition, Total orders and Total visits are separately calculated metrics altogether.|

Since there's no logical and concrete method to determine if a calculated metric makes sense in reporting, the metric total is omitted altogether. If you want to obtain a grand total, you can do one of the following:

* Create a calculated metric that includes the Total versions of the metrics that you're looking to include.
* Create a Data Extract report, which can be scheduled.
* Create a data request within [!DNL ReportBuilder].
* Use [!DNL Analysis Workspace] (see below).

## Calculated metric totals in [!DNL Analysis Workspace]

When you view data in Analysis Workspace, calculated metric totals are displayed in most cases. In some cases, providing a total is not possible, such as when the rows of the report are of mixed format (e.g. decimal and currency).

When totals are displayed, they are often calculated server-side, which means that the total de-duplicates metrics like visits or visitors. Under certain circumstances, calculated metrics are generated client-side by summing across rows of the table, which means the total does not de-duplicate metrics like visits or visitors. This occurs:

* When [static rows](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) are used in Freeform tables and the **[!UICONTROL Show as sum of current rows]** option (default) is selected.
* In the [Donut visualization](/help/analyze/analysis-workspace/visualizations/donut.md), so that numbers add up to 100%.

For more information on totals in Analysis Workspace, visit [Workspace totals](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=en#static-row-total).
