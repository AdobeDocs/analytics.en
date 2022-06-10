---
title: Average page views per visit
description: The average number of times a given dimension item appeared in a visit.
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
---
# Average page views per visit

The 'Average page views per visit' dimension shows how many page views occurred on average against your desired dimension. For time-based dimensions, you can see how the average number of page views within a visit trends over time. This metric is helpful when you want to understand how frequently dimension items appear in a visit.

>[!TIP]
>
>Use this metric alongside another metric (such as [Visits](visits.md)) to obtain better insights. If you use this metric by itself, you get dimension items containing anomaly page views per visit, which is typically not valuable.

## How this metric is calculated

This metric is calculated using the formula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Percentages above 100%

This metric frequently contains percentages above 100%. The denominator is the entire dimension's average page views per visit, and the numerator is the dimension item's average page views per visit. If the entire dimension's average page views per visit is lower than a given dimension item's average page views per visit, you'll see percentages above 100%. Sorting ranked reports by this metric shows anomaly average page views per visit values, which is typically not valuable. Adobe recommends sorting by another metric, such as [Visits](visits.md), in ranked reports.
