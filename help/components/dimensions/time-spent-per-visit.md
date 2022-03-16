---
title: Time spent per visit (dimensions)
description: The total amount of time the visit took.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
---
# Time spent per visit

*This help page describes how 'Time spent per visit' works as their respective dimensions. See the [Time spent per visit](../metrics/time-spent-per-visit.md) metric for more information.*

The 'Time spent per visit' dimensions record the amount of time a visitor spent on the entire visit. It uses the following steps to measure calculation:

1. Look at the timestamp of the first hit of the visit.
2. Compare this hit with the timestamp of the last hit of the visit.
3. The amount of time that elapsed between these two hits contributes to the time spent.

These dimensions are valuable when you want to understand how long visitors interact with your site in general.

>[!TIP]
>
>Time spent requires at least two hits in a visit to measure time. Visits that consist of a single hit do not appear in this dimension.

This dimension is visit-based, meaning that the value applies to every hit within the visit and doesn't change. Compare this dimension to [Time spent on page](time-spent-on-page.md), which is a hit-based dimension.

This dimension is related to the [Average time spent on site](../metrics/average-time-on-site.md) and [Time spent per visit](../metrics/time-spent-per-visit.md) metrics.

## Populate this dimension with data

These dimensions work out of the box for all implementations. If a report suite contains data, these dimensions work.

## Dimension items

Multiple dimensions exist for time spent per visit:

* **Time spent per visit - bucketed**: The amount of time is bucketed. Dimension items range from `"Less than 1 minute"` to `"More than 15 hours"`. Visits typically don't last longer than 12 hours; however, visits can exceed 12 hours if using timestamped hits or data sources.
* **Time spent per visit - granular**: Each number of seconds is a unique dimension item. This dimension is not available in Reports & Analytics or Data Warehouse.

See [Time spent overview](../metrics/time-spent.md) for more general information on time spent.
