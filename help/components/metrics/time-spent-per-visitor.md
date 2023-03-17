---
title: Time spent per visitor (seconds)
description: The 'Time spent per visitor (seconds)' metric shows the average amount of time that visitors interact with a given dimension item during a visitor's entire lifetime.
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
---
# Time spent per visitor (seconds)

The [!UICONTROL Time spent per visitor (seconds)] metric shows the average amount of time that visitors interact with a given dimension item during a visitor's entire lifetime.

This metric is not available in Data Warehouse due to its different processing architecture.

## How this metric is calculated

This metric uses the formula [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Percentages above 100%

This metric frequently contains percentages above 100%. The denominator is the entire dimension's time spent per visitor, and the numerator is the dimension item's time spent per visitor. If the entire dimension's time spent per visitor is lower than a given dimension item's time spent per visitor, you'll see percentages above 100%. Sorting ranked reports by this metric shows anomaly time spent per visitor values, which is typically not valuable. Adobe recommends sorting by another metric, such as [Visits](visits.md), in ranked reports.

See [Time spent overview](time-spent.md) for more general information on time spent.
