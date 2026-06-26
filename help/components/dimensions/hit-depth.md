---
title: Hit depth
description: The number of hits into the visit.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
TQID: https://experienceleague.adobe.com/dH1ItdXZTw9vcqvej3VOQDM-J9FFA38f4bq8HTJbKMo
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
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
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
# Hit depth

The 'Hit depth' [dimension](overview.md) reports how far into a visit a given hit is. This dimension is valuable in understanding how far into a visit that visitors perform actions on your site. Hit depth counts all types of hits, including page views ([`t()`](/help/implement/vars/functions/t-method.md)) and link tracking hits ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include the string `"Hit Depth"` followed by a number representing the number of hits into the visit. The dimension item of `"Hit Depth 1"` represents the first hit of the visit, while the dimension item `"Hit Depth 8"` represents the 8th hit of the visit.

>[!NOTE]
>
>Adobe Analytics records timestamps at only second-level precision. For hits that share the same timestamp second, Adobe cannot guarantee that the order reflected in reporting is the same as the order in which the hits happened. If millisecond-level precision is a priority for your organization, consider using Customer Journey Analytics.

## Comparison to visit depth

Hit depth counts all types of hits, including page view and link tracking hits. Visit depth only increments for page view hits, _and_ the [Page](page.md) dimension item is not the same as the value on the previous page. Visit depth is also a visit-based dimension, meaning it is the same value for all hits in the visit. The following table outlines an example visit and how it considers hit depth + visit depth:

  | Page sequence | Hit depth | Counts toward visit depth? | Visit depth |
  | --- | --- | --- | --- |
  | Home page | 1 | Yes | 4 |
  | Product page | 2 | Yes | 4 |
  | Home page | 3 | Yes | 4 |
  | Custom link click | 4 | No (custom link) | 4 |
  | Custom link click | 5 | No (custom link) | 4 |
  | Product page | 6 | Yes | 4 |
  | Custom link click | 7 | No (custom link) | 4 |
  | Product page | 8 | No (same as previous page) | 4 |
