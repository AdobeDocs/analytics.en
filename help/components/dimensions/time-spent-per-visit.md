---
title: Time spent per visit (dimensions)
description: The total amount of time the visit took.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
TQID: 'https://experienceleague.adobe.com/jtBAAq-Pe0PyCQJPwvzwnK9eLv14CxTvrVQP4lvWy7k'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Time spent per visit

*This help page describes how 'Time spent per visit' works as their respective [dimensions](overview.md). See the [Time spent per visit](../metrics/time-spent-per-visit.md) metric for more information.*

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
* **Time spent per visit - granular**: Each number of seconds is a unique dimension item. This dimension is not available in Data Warehouse.

See [Time spent overview](../metrics/time-spent.md) for more general information on time spent.
