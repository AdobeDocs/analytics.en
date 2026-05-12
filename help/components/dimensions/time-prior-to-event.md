---
title: Time prior to event
description: The amount of time between the metric and the first hit of the visit.
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
TQID: https://experienceleague.adobe.com/vO3S-yZwV7KSLmIzRfwNDrVaB3NzpsIocmHsAaamfj0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Time prior to event

The 'Time prior to event' [dimension](overview.md) reports the amount of time that passed between the first hit of the visit and the desired metric. This dimension is useful to determine the amount of time it takes to hit a success event, such as a form submission or a purchase.

## Populate this dimension with data

While this dimension technically works out of the box for all implementations, it works best with custom and purchase events. Adobe recommends implementing custom events on your site. If you implement custom events, no additional implementation is required for this dimension.

## Dimension items

Dimension items include time-based buckets ranging from `"Less than 1 minute"` to `"More than 15 hours"`. For example, if it took a visitor 23 minutes from their first hit to a purchase, it would belong under the `"10 to 30 minutes"` dimension item. The buckets cannot be customized for this metric.
