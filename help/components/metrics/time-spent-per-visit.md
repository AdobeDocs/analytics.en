---
title: Time spent per visit (metrics)
description: The amount of time spent per visit for the dimension item.
feature: Metrics
exl-id: 0f951196-66a2-4733-bb62-4555a9331efb
---
# Time spent per visit (seconds)

*This help page describes how 'Time spent per visit' works as a metric. See the [Time spent per visit](../dimensions/time-spent-per-visit.md) dimension for more information.*

The 'Time spent per visit (seconds)' metric shows the average amount of time that visitors interact with a given dimension item during each visit.

This metric is not available in Data Warehouse due to its different processing architecture.

## How this metric is calculated

This metric uses the formula [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`.

## Comparison to Average time on site

This metric and [Average time spent on site](average-time-on-site.md) are similar, but have several key differences. Both metrics use 'Total seconds spent' as the numerator. However, 'Average time on site' uses the sequences that include a dimension item as its denominator. Time spent per visit uses visit count as its denominator.

As a result, these metrics yield similar results at a visit level, but are different at a hit level.

## Percentages above 100%

This metric frequently contains percentages above 100%. The denominator is the entire dimension's time spent per visit, and the numerator is the dimension item's time spent per visit. If the entire dimension's time spent per visit is lower than a given dimension item's time spent per visit, you'll see percentages above 100%. Sorting ranked reports by this metric shows anomaly time spent per visit values, which is typically not valuable. Adobe recommends sorting by another metric, such as [Visits](visits.md), in ranked reports.

See [Time spent overview](time-spent.md) for more general information on time spent.
