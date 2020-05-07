---
title: Time spent per visit
description: The total amount of time the visit took.
---

# Time spent per visit

The 'Time spent per visit' dimension records the amount of time a visitor spent on the entire visit. It uses the following steps to measure calculation:

1. Look at the timestamp of the first hit of the visit.
2. Compare this hit with the timestamp of the last hit of the visit.
3. The amount of time that elapsed between these two hits contributes to the time spent.

This dimension is valuable when you want to understand how long visitors interact with your site in general.

>[!TIP] Time spent requires at least two hits to measure time. Visits that consist of a single hit do not appear in this dimension.

This dimension is visit-based, meaning that the value applies to every hit within the visit and doesn't change. Compare this dimension to [Time spent on page](time-spent-on-page.md), which is a hit-based dimension.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension values

Multiple dimensions exist for time spent per visit:

* **Time spent per visit - bucketed**: The amount of time is bucketed. Dimension values range from `"Less than 1 minute"` to `"More than 15 hours"`. Visits typically don't last longer than 12 hours; however, visits can exceed 12 hours if using timestamped hits or data sources.
* **Time spent per visit - granular**: Each number of seconds is a unique dimension value.