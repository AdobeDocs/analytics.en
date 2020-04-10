---
title: Hit depth
description: The number of hits into the visit.
---

# Hit depth

The 'Hit depth' dimension reports how far into a visit a given hit is. This dimension is valuable in understanding how far into a visit that visitors perform actions on your site.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension values

Dimension values include the string "Hit Depth" followed by a number representing the number of hits into the visit. The dimension value of "Hit Depth 1" represents the first hit of the visit, while the dimension value "Hit Depth 8" represents the 8th hit of the visit.

## Comparison to other dimensions

* [**Visit depth**](visit-depth.md): Hit depth counts all types of hits, including page view and link tracking hits. Visit depth only increments for page view hits, _and_ the [Page](page.md) dimension value is not the same as the value on the previous page. For example:

  | Page sequence | Hit depth | Visit depth |
  | --- | --- | --- |
  | Home page | 1 | 1 |
  | Product page | 2 | 2 |
  | Home page | 3 | 3 |
  | Custom link click | 4 | 3 |
  | Custom link click | 5 | 3 |
  | Product page | 6 | 4 |
  | Custom link click | 7 | 4 |
  | Product page | 8 | 4 |
