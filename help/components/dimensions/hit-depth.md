---
title: Hit depth
description: The number of hits into the visit.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
---
# Hit depth

The 'Hit depth' dimension reports how far into a visit a given hit is. This dimension is valuable in understanding how far into a visit that visitors perform actions on your site. Hit depth counts all types of hits, including page views ([`t()`](/help/implement/vars/functions/t-method.md))and link tracking hits ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include the string `"Hit Depth"` followed by a number representing the number of hits into the visit. The dimension item of `"Hit Depth 1"` represents the first hit of the visit, while the dimension item `"Hit Depth 8"` represents the 8th hit of the visit.

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
