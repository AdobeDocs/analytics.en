---
title: Average time  on site
description: The average amount of time a given dimension item existed between hits.
feature: Metrics
exl-id: bf9056e2-4f6d-4c4f-b641-d3146ce269ff
---
# Average time on site

The 'Average time on site' metric show the the amount of time that passed between hits for a given dimension item. This metric is helpful when you want to see average time spent for specific dimension items. You can also trend this metric over time to see how overall time spent changes. This metric displays in `HH:MM:SS` format.

This metric is related to the [Time spent per visit](../dimensions/time-spent-per-visit.md) dimension.

## How this metric is calculated

For a given dimension item, take the timestamp of each hit where that dimension item exists. Compare it with the timestamp of the next hit in the visit. If the hit doesn't have a subsequent hit, do not include it in this metric. Out of all the time spent for the dimension item, divide them all by the number of "sequences" for that dimension item. A "sequence" is where a dimension item is the same for one or more consecutive hits. This resulting number is the metric displayed in reports.

For example, consider the following visit:

| `Timestamp` | `Page` |
| --- | --- |
| `12:03:00` | `Home page` |
| `12:04:20` | `Product page A` |
| `12:05:30` | `Product page A` |
| `12:07:00` | `Product page B` |
| `12:07:40` | `Product page A` |
| `12:08:10` | `Checkout` |
| `12:10:00` | `Purchase` |
| `12:25:00` | `Home page` |
| `12:25:40` | `Product page A` |


If you want average time on site for the dimension item `Product page A`, first take the amount of time lapsed between hits for that dimension:

* **12:04:20 - 12:05:30** - 1 minute 10 seconds
* **12:05:30 - 12:07:00** - 1 minute 30 seconds
* **12:07:40 - 12:08:10** - 30 seconds
* **12:25:40 - ?** - Not included

The total amount of time spent for `Product page A` is `00:03:10`. There were two sequences in this visit; the first sequence for the two consecutive values, and the second prior to checkout. The last hit of the visit is not a sequence, since there is no end timestamp.

The average time on site for `Product page A` is `00:01:35`.

>[!NOTE]
>
>This metric shows a value of `"Invalid"` if the dimension item contains only hits that were last in a visit. This metric requires a subsequent hit to track time spent.

## Average time spent on site (seconds)

The 'Average time spent on site (seconds)' metric shows the same data presented as an integer instead of in `HH:MM:SS` format. This metric is most valuable as a component within calculated metrics.

## Breakdown totals don't match the parent line item

The 'Average time on site' metric use unbroken sequences of a given dimension. The breakdown dimension doesn't depend on the parent dimension when calculating these sequences. For example, consider the following visit:

| `Timestamp` | `Page name` | `Site section` |
| --- | --- | --- |
| `12:00:00` | `Home` | `Foxes` |
| `12:00:30` | `Product` | `Foxes` |
| `12:02:10` | `Home` | `Foxes` |
| `12:02:20` | `(None; exit link click)` | `(None; exit link click)` |

Calculating average time on site for the dimension item `Home` would use the following calculation:

```text
(30 + 10) / 2 = 20 seconds average time on site
```

If you applied a breakdown using the [Site sections](../dimensions/site-section.md) dimension, it would use the following calculation:

```text
(30 + 10) / 1 = 40 seconds average time on site
```

Since there was a single sequence in the breakdown dimension, it uses a different denominator than its parent dimension. These metrics usually provide similar results at a visit level, but can be different at a hit level.

## Percentages above 100%

This metric frequently contains percentages above 100%. The denominator is the entire dimension's average time on site, and the numerator is the dimension item's average time on site. If the entire dimension's average time on site is lower than a given dimension item's average time on site, you'll see percentages above 100%. Sorting ranked reports by this metric shows anomaly average time on site values, which is typically not valuable. Adobe recommends sorting by another metric, such as [Visits](visits.md), in ranked reports.

See [Time spent overview](time-spent.md) for more general information on time spent.
