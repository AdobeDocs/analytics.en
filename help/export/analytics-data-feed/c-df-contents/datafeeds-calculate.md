---
description: Describes how to calculate common metrics using data feeds.
keywords: Data Feed;job;metrics;pre column;post column;bots;date filtering;event string;common;formulas
title: Calculate metrics
feature: Data Feeds
exl-id: f9b0d637-7a6e-416a-adff-3c7e533bfac7
---
# Use data feeds to calculate common metrics

Describes how to calculate common metrics using data feeds.

>[!NOTE]
>
>Hits normally excluded from Adobe Analytics are included in data feeds. Use `exclude_hit > 0` to remove excluded hits from queries on raw data. Data sourced data are also included in data feeds. If you want to exclude data sources, exclude all rows with `hit_source = 5,7,8,9`.

## Page views

1. Count the number of rows where a value is in `post_pagename` or `post_page_url`.

## Visits

1. Concatenate `post_visid_high`, `post_visid_low`, `visit_num`, and `visit_start_time_gmt`.
1. Count the unique number of values.

>[!NOTE]
>
>Internet irregularities, system irregularities, or the use of custom visitor IDs can rarely use the same `visit_num` values for different visits. Use `visit_start_time_gmt` when counting visits to make sure that these visits are counted.

## Visitors

All methods Adobe uses to identify unique visitors (custom visitor ID, Experience Cloud ID service, etc.) are all ultimately calculated as a value in `post_visid_high` and `post_visid_low`. The concatenation of these two columns can be used as the standard of identifying unique visitors regardless of how they were identified as a unique visitor. If you would like to understand which method Adobe used to identify a unique visitor, use the column `post_visid_type`.

1. Concatenate `post_visid_high` and `post_visid_low`.
2. Count the unique number of values.

## Custom, download, or exit links

1. Count the number of rows where:
   * `post_page_event = 100` for custom links
   * `post_page_event = 101` for download links
   * `post_page_event = 102` for exit links

## Custom events

All metrics are counted in the `post_event_list` column as comma-delimited integers. Use `event.tsv` to match numeric values with the desired event. For example, `post_event_list = 1,200` indicates that the hit contained a purchase event and custom event 1.

1. Count the number of times the event lookup value appears in `post_event_list`.

## Time spent

Hits must first be grouped by visit, then ordered according to the hit number within the visit.

1. Concatenate `post_visid_high`, `post_visid_low`, `visit_num`, and `visit_start_time_gmt`.
2. Sort by this concatenated value, then apply a secondary sort by `visit_page_num`.
3. If a hit is not the last one in a visit, subtract the `post_cust_hit_time` value from the subsequent hit's `post_cust_hit_time` value.
4. This number is the amount of time spent (in seconds) for the hit. Filters can be applied to focus on dimension items or events.

## Orders, units, and revenue

If a hit's `currency` value doesn't match a report suite's currency, it is converted using that day's conversion rate. The column `post_product_list` uses the converted currency value, so all hits use the same currency in this column.

1. Exclude all rows where `duplicate_purchase = 1`.
2. Include only rows where `event_list` contains the purchase event.
3. Parse the `post_product_list` column to extract all price data. The `post_product_list` column is formatted the same as the `s.products` variable.
4. Calculate the desired metric:
   * Count the number of rows to calculate Orders
   * Sum the number of `quantity` in the product string to calculate Units
   * Sum the number of `price` in the product string to calculate revenue
