---
title: Average page views per visit
description: The average number of times a given dimension item appeared in a visit.
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
TQID: https://experienceleague.adobe.com/sospsPhk77O5qOLcMLmu7gB7rvlxbp8rGqB39LCnQ5g
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
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# Average page views per visit

The 'Average page views per visit' dimension shows how many page views occurred on average against your desired dimension. For time-based dimensions, you can see how the average number of page views within a visit trends over time. This [metric](overview.md) is helpful when you want to understand how frequently dimension items appear in a visit.

>[!TIP]
>
>Use this metric alongside another metric (such as [Visits](visits.md)) to obtain better insights. If you use this metric by itself, you get dimension items containing anomaly page views per visit, which is typically not valuable.

## How this metric is calculated

This metric is calculated using the formula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Percentages above 100%

This metric frequently contains percentages above 100%. The denominator is the entire dimension's average page views per visit, and the numerator is the dimension item's average page views per visit. If the entire dimension's average page views per visit is lower than a given dimension item's average page views per visit, you'll see percentages above 100%. Sorting ranked reports by this metric shows anomaly average page views per visit values, which is typically not valuable. Adobe recommends sorting by another metric, such as [Visits](visits.md), in ranked reports.
