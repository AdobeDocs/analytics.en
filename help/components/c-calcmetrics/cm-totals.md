---
title: Calculated metrics totals
seo-title: Calculated metrics totals
description: Learn how calculated metrics totals differ in Analytics tools
seo-description: How calculated metrics totals are calculated
---

# Calculated metrics totals

How calculated metric totals are displayed differs between [DNL Reports &amp; Analytics] and [DNL Analysis Workspace]. This section explains the differences.

## Calculated metrics totals in [!DNL Reports & Analytics]

When you view reports in [!DNL Reports & Analytics], calculated metrics always display `n/a` under the total. Since all calculated metrics are user-defined, there are many circumstances where this total doesn't make sense. Consider the following example:

Your organization has created the calculated metric [orders] / [visits] to determine the percentage of visits that purchased something on your site. If you brought this metric into a products report, several products are attributed to a single order. And, several products are attributed to a single visit. If a calculated metric total was included in this report, the following questions arise:

|Question| Answer|
|---|---|
|Does summing the line items make sense?|It doesn't, since multiple products can be included in a single order, and multiple products can be included in a single visit. If the line items were aggregated, total orders and total visits would not match the actual total orders and total visits.|
|Does taking total orders and total visits make sense?|It doesn't, as the total doesn't match the sum of the individual line items. In addition, Total orders and Total visits are separately calculated metrics altogether.|

Since there's no logical and concrete method to determine if a calculated metric makes sense in reporting, the metric total is omitted altogether. If you want to obtain a grand total, you can do one of the following:

* Create a calculated metric that includes the Total versions of the metrics that you're looking to include.
* Create a Data Extract report, which can be scheduled.
* Create a data request within ReportBuilder.
* Use Analysis Workspace (see below).

## Calculated metric totals in [!DNL Analysis Workspace]

In Analysis Workspace, under certain circumstances, calculated metrics are summed to display a total:

* When there are [static rows](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) and the **[!UICONTROL Calculate totals by summing the values currently in each column]** option (default) is selected.
* In the [Donut visualization](/help/analyze/analysis-workspace/visualizations/donut.md).
* In the [Summary Change visualization](/help/analyze/analysis-workspace/visualizations/summary-number-change.md).
