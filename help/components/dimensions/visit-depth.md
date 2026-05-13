---
title: Visit depth
description: Visit-based dimension that reports the depth of the visit.
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
TQID: https://experienceleague.adobe.com/mT5dQzR6edNpvU6Fbf9LlLwQuxW6RA-ZCZJDaIFkyAw
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
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
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
# Visit depth

The 'Visit depth' [dimension](overview.md) reports the number of page views the visitor saw in the entire visit. Visit depth increases only if the hit is a page view, and the [Page](page.md) dimension is not the same as the last page view's dimension item. It is a visit-based dimension, meaning that it contains the same value for the entire visit. This variable is set for all hits in a visit after that visit concludes.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include the string `"Pages per visit"` followed by a number representing the number of pages in the visit. The dimension item of `"Pages per visit: 1"` represents a single-page visit, while the dimension item `"Pages per visit: 8"` represents a visit with 8 page views (and any number of link tracking calls).

## Comparison to hit depth

See [Hit depth](hit-depth.md) for a comparison between dimensions.
