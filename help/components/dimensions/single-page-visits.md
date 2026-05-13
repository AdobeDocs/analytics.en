---
title: Single page visits (dimensions)
description: A flag indicating that the visit consisted of a single page.
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
TQID: https://experienceleague.adobe.com/mMxxlVpQi7IsSuxSZGijnvWeoqCa-ybf8otPRDf6AyQ
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
# Single page visits

*This help page describes how 'Single page visits' works as a [dimension](overview.md). See the [Single page visits](../metrics/single-page-visits.md) metric for more information.*

The 'Single page visits' dimension reports the number of visits that consisted of a single unique [Page](page.md) dimension item. It is the dimension form of the [Single page visits](../metrics/single-page-visits.md) metric.

This dimension is most commonly used as a component within [segmentation](../segmentation/seg-home.md). It is not typically used as a dimension in reports.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

The only dimension item is `"Enabled"`. If a visit consists of a single page, the hit is set to this value. All other hits are omitted from this report.
