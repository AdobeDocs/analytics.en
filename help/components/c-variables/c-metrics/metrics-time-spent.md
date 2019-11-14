---
description: Adobe Analytics offers various Time Spent metrics and dimensions. Find out what they are and how they are calculated.
solution: Analytics
title: Time Spent
topic: Metrics
---

# Time spent metrics

Adobe Analytics offers several ways to determine time spent in Analytics reports. In most cases, time spent is calculated using the following steps:

1. For a given hit, look at the timestamp and dimension value.
1. Compare this hit with the timestamp of the next hit in the visit.
1. The amount of time that elapsed between these two hits contributes to the time spent for that dimension value.

When viewing time spent metrics, keep the following in mind:

* Time spent takes allocation and expiration into account.
* Both page views and link tracking hit types are considered when calculating time spent data.
* Time spent is not measured during the last hit of the visit, since there is no subsequent image request to measure elapsed time.
* Bounces cannot measure time spent, since the visit consists of a single hit.

## Total seconds spent

The total amount of time all visitors interacted with a dimension value, measured in seconds.

## Time spent per visit (seconds)

The average amount of time visitors interact with a dimension value in a visit. Its approximate calculation is `Total seconds spent / (Visits - Bounces)`.

## Time spent per visitor (seconds)

The average amount of time visitors interact with a dimension value across the visitor's lifetime. Its approximate calculation is `Total seconds spent / (Unique Visitors - Bounces)`.

## Average time spent on site (seconds)

The average amount of time spent on your site, typically paired with a date dimension. Although this metric usually shows time spent trended over time, it can also be used with dimensions as an alternative calculation to Time spent per visit. Its approximate calculation is `Total seconds spent / (Sequences - Bounces)`. Sequences are a series of hits where the dimension value did not change.

> [!NOTE] Time spent per visit and Average time spent on site are similar metrics. The difference between these two metrics is their denominator; time spent per visit uses `visits - bounces`, while Average time spent on site uses `sequences - bounces`. On a visit level, these metrics appear similar, but can have some differences at a hit level.

## Average time spent on page

Only available in Report Builder. In most cases, use Time spent per visit instead.
