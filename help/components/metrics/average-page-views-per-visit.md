---
title: Average page views per visit
description: The average number of times a given dimension value appeared in a visit.
---

# Average page views per visit

The 'Average page views per visit' dimension shows how many page views occurred on average against your desired dimension. For time-based dimensions, you can see how the average number of page views within a visit trends over time. This metric is helpful when you want to understand how frequently dimension values appear in a visit.

## How this metric is calculated

This metric is calculated using the formula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Percentages above 100%

This metric frequently contains percentages above 100%. The denominator is the entire dimension's average page views per visit, and the numerator is the dimension value's average page views per visit. If the entire dimension's average page views per visit is lower than a given dimension value's average page views per visit, you'll see percentages above 100%.
