---
title: Single access
description: The number of times a dimension item did not change in a visit.
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
---
# Single access

The 'Single access' metric shows the number of visits where the dimension item contained only a single unique value for the entire visit. This metric is helpful in context of any dimension where you want to see which dimension items stagnate during a visit.

## How this metric is calculated

This metric counts visits where the dimension item contained a single unique value. You can set the dimension item multiple times or have it persist and still count as a single access. As soon as a dimension item changes to a second unique value, the visit no longer qualifies as a single access.

## Difference between 'Single access' and 'Single page visit'

In context of the [Page](../dimensions/page.md) dimension, 'Single access' and 'Single page visits' are exactly identical. Their differences emerge when you use other dimensions.

* **Single access**: Shows the number of visits where the given dimension item did not change for the entire visit. It is contextual to the dimension that you use in your project.
* **Single page visit**: Shows the number of visits where the 'Page' dimension did not change for the entire visit. Even though you use another dimension in your report, it still counts visits that contain a single unique 'Page' dimension item.

For example, consider the following example two hit visits. The dimension in your report is [Site section](../dimensions/site-section.md).

* A visitor hits two pages, but they are both in the same site section. Since site section remained the same through the visit, it counts as a Single access. It does not count as a Single page visit because the visit contains more than one unique Page dimension item.
* A visitor hits two pages in different site sections, but both pages just happen to be named the same. The visit does not count as a Single access because there were two unique site section values. It counts as a Single page visit because there was a single unique Page dimension item.
