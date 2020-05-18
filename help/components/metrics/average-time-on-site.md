---
title: Average time  on site
description: The average amount of time a given dimension value existed between hits.
---

# Average time on site

The 'Average time on site' metric show the the amount of time that passed between hits for a given dimension value. This metric is helpful when you want to see average time spent for specific dimension values. You can also trend this metric over time to see how overall time spent changes. This metric displays in `HH:MM:SS` format.

This metric is related to the [Time spent per visit](../dimensions/time-spent-per-visit.md) dimension.

## How this metric is calculated

For a given dimension value, take the timestamp of each hit where that dimension value exists. Compare it with the timestamp of the next hit in the visit. If the hit doesn't have a subsequent hit, do not include it in this metric. Out of all the time spent for the dimension value, average them all. This resulting average is the metric displayed in reports.

For example, consider the following visit:

```text
1:03 PM: Home page
1:06 PM: Product page A
1:07 PM: Product page B
1:10 PM: Product page A
1:12 PM: Checkout
1:13 PM: Purchase
1:25 PM: Home page
1:26 PM: Product page A
```

If you want average time on site for the dimension value `Product page A`, first take the amount of time lapsed between hits for that dimension:

```text
1:06 - 1:07: 1 minute
1:10 - 1:12: 2 minutes
1:26 - ?: Not included in calculation
```

The average between the values is the average time spent on site. In this case, it is `00:01:30`. The resulting report would look similar to the following:

| `Page`| `Average time on site` |
| --- | --- |
| `Purchase` | `00:12:00` |
| `Product page B` | `00:03:00` |
| `Home page` | `00:02:00` |
| `Product page A` | `00:01:30` |
| `Checkout` | `00:01:00` |

>[!NOTE] The above example rounds timestamps to the nearest minute to simplify calculations. Data collected in report suites considers timestamps down to the second.

## Average time spent on site (seconds)

The 'Average time spent on site (seconds)' metric shows the same data presented as an integer instead of in `HH:MM:SS` format. This metric is most valuable as a component within calculated metrics.

## Percentages above 100%

This metric frequently contains percentages above 100%. The denominator is the entire dimension's average time on site, and the numerator is the dimension value's average time on site. If the entire dimension's average time on site is lower than a given dimension value's average time on site, you'll see percentages above 100%. Sorting ranked reports by this metric shows anomaly average time on site values, which is typically not valuable. Adobe recommends sorting by another metric, such as [Visits](visits.md), in ranked reports.