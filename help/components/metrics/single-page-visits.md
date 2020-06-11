---
title: Single page visits
description: The number of times that the 'Page' dimension value did not change in a visit.
---

# Single page visits

*This help page describes how 'Single page visits' works as a metric. See the [Single page visits](../dimensions/single-page-visits.md) dimension for more information.*

The 'Single page visits' metric shows the number of visits where the [Page](../dimensions/page.md) dimension value contained only a single unique value for the entire visit. This metric is helpful in context of dimensions where you want to see short visits, but not have as stringent rules as [Bounces](bounces.md).

## How this metric is calculated

This metric counts the number of visits where the 'Page' dimension value contained only a single unique value for the entire visit. If a visitor reloads the page or fires link tracking calls, it still counts as a single page visit. As soon as the Page dimension changes to a second unique value, the visit no longer qualifies as a single page visit.

See [Single access](single-access.md) for a comparison between metrics.
