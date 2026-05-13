---
title: Days since last purchase
description: The number of days between the current hit and the last purchase that they made.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
TQID: https://experienceleague.adobe.com/q86bc1bMRctUBe7dFEJaALsq0GjALFQQtKU9cRpRkoU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Days since last purchase

The 'Days since last purchase' [dimension](overview.md) measures the amount of time passed between the current hit of the visitor and their most recent purchase at that time. This dimension helps you understand behavior visitors make after purchasing something on your site.

Visitors that have never purchased something are not included in this dimension. Additionally, hits fired before a visitor's first purchase are not included either. Only hits after the visitor's first purchase are included.

## Populate this dimension with data

Adobe automatically populates this dimension based on the [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) event in your implementation. If you implement the `purchase` event on your site, this dimension always works.

## Dimension items

Dimension items include the number of days between a visitor's most recent purchase and the current hit. Each number of days is a separate dimension item, with "Same day" occurring where a visitor's most recent purchase and the current hit happened on the same day.
