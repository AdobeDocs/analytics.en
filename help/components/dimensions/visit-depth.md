---
title: Visit depth
description: Visit-based dimension that reports the depth of the visit.
---

# Visit depth

The 'Visit depth' dimension reports the number of page views the visitor saw in the entire visit. Visit depth increases only if the hit is a page view, and the [Page](page.md) dimension is not the same as the last page view's dimension value. It is a visit-based dimension, meaning that it contains the same value for the entire visit. This variable is set for all hits in a visit after that visit concludes.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension values

Dimension values include the string `"Pages per visit"` followed by a number representing the number of pages in the visit. The dimension value of `"Pages per visit: 1"` represents a single-page visit, while the dimension value `"Pages per visit: 8"` represents a visit with 8 page views (and any number of link tracking calls).

## Comparison to hit depth

See [Hit depth](hit-depth.md) for a comparison between dimensions.