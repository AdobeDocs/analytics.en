---
description: Steps you can take to prepare to use data sources
subtopic: Data sources
title: Preparing to use Data Sources
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 3cad7c33-f31c-41a2-9dd2-9535713c7620
---
# Prepare to use Data Sources

Steps you can take to prepare to use data sources

* [Identify and Name the Metrics](/help/import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135) 
* [Identify the Data Dimensions](/help/import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A) 
* [Campaign Tracking Code](/help/import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1) 
* [Transaction ID](/help/import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7) 
* [Identify a Valid Date Range for Data Source Data](/help/import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## Identify and Name the Metrics {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

It is important to understand the metrics or measurements that are contained in your data sources, such as *`Off-line Sales Revenue by Product`*, *`Returns by Product`*, or *`Ad Impressions by Campaign`*. These are the names that you can associate with report metrics (events, props, and eVars).

After you determine the appropriate metric-to-event mappings for the Data Sources data, rename the events with descriptive names appropriate for the associated Data Sources metric.

See [Success Events](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) in Admin Tools Help.

>[!NOTE]
>
>Adobe strongly recommends using new, empty events with Data Sources data, but in rare cases it might make sense to use a pre-existing event.

## Identify the Data Dimensions {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

Identify and gather the data (reports) that you want to use to breakdown the metrics imported through Data Sources. This data is known as *`data dimensions`*.

For example, if a Data Sources metric measures ad impressions, your data dimension is likely the campaign tracking code. If you are measuring off-line sales, you might want to use product code (or SKU) as your data dimension.

You can define multiple data dimensions to a metric, but each metric must provide a relevant value, or combination of values, for each associated data dimension. For example, if you import an Off-line Sales metric and associate it with *`Product`* and *`Partner`* data dimensions, the Off-line Sales metric must be relevant for each combination of product and partner (for example, Total Revenue).

>[!NOTE]
>
>It is possible to import Total metrics that cannot be broken down by any data dimension.

After you define the data dimensions to use with a data source, integrate the dimensions data into marketing reports by mapping it to a variable. Use either standard reports (for example, Product, Tracking Code, Search Keyword) or Conversion Traffic variables (eVars).

When using eVars, you can use either existing eVars or new eVars as data dimensions. After selecting an eVar to receive a data dimension from Data Sources, make sure that you name them appropriately.

See [Success Events](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) in Analytics Help.

## Campaign Tracking Code {#section_468222796FF449ABAA90D88EB3264CB1}

In addition to importing success events, you can optionally import associated eVar values. For example, if you track online activity with a Campaign Tracking Code, and have Campaign Tracking Codes for the offline metrics, you can import the metrics with Campaign Tracking Codes. This approach allows you to view both online and offline metrics in Campaign reports.

If you do not import Data Sources metrics with an associated eVar value, you cannot view Data Source metrics broken down by eVars. Rather, you can only see Total metrics.

## Transaction ID {#section_D9513C1204B7496C9B738C5B12CCCFC7}

The Transaction ID is used to connect an online event to an offline event.

## Identify a Valid Date Range for Data Source Data {#section_03AAB1291BDC4403BDC50905A78FDB71}

After you define your Data Sources metrics (Custom Events) and data dimensions (eVars), review the date range of the Data Source data that you want to import. You cannot import Data Sources that fall outside the range of your existing reporting data.

For example, you cannot import Data Source data from before you implemented on-line data tracking. Data Sources data should be broken down by day.
