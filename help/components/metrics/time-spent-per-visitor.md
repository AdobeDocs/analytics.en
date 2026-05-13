---
title: Time spent per visitor (seconds)
description: The 'Time spent per visitor (seconds)' metric shows the average amount of time that visitors interact with a given dimension item during a visitor's entire lifetime.
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
TQID: https://experienceleague.adobe.com/NFmA2Q80h2WOTRwoJ882aFMG60y2HKngR0Ew0qnxb8o
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Time spent per visitor (seconds)

The [!UICONTROL Time spent per visitor (seconds)] [metric](overview.md) shows the average amount of time that visitors interact with a given dimension item during a visitor's entire lifetime.

This metric is not available in Data Warehouse due to its different processing architecture.

## How this metric is calculated

This metric uses the formula [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Percentages above 100%

This metric frequently contains percentages above 100%. The denominator is the entire dimension's time spent per visitor, and the numerator is the dimension item's time spent per visitor. If the entire dimension's time spent per visitor is lower than a given dimension item's time spent per visitor, you'll see percentages above 100%. Sorting ranked reports by this metric shows anomaly time spent per visitor values, which is typically not valuable. Adobe recommends sorting by another metric, such as [Visits](visits.md), in ranked reports.

See [Time spent overview](time-spent.md) for more general information on time spent.
