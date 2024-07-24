---
title: Activity Map Region
description: The region on your site that was clicked.
feature: Dimensions
role: User, Admin
exl-id: e262e537-ce73-492a-8ab3-b88cd77cb8c5
---
# Activity Map Region

The 'Activity Map Region' [dimension](overview.md) displays the regions on your site that were clicked the most. This dimension is useful when you want to compare clicks across overarching regions of your site instead of individual links. It is also helpful for areas of your site that serve dynamic content. For example, if you have a front page with rotating news articles, using the [Activity Map Link](activity-map-link.md) dimension would be difficult because link text constantly changes. However, since those links use the same region, you can analyze the performance of that area even though individual links might change each day.

## Populate this dimension with data

This dimension retrieves data from the [Context data variable](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.region`. If your implementation uses [Activity Map](/help/analyze/activity-map/overview.md), this context data variable automatically collects data when links are clicked.

For a given link that was clicked, check the parent DOM element for the following (in order):

* A value in the attribute set by [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) - set to the `id` attribute by default
* A value in the `aria-label` attribute when the attribute `role="region"`
* The semantic elements `<header>`, `<main>`, `<footer>`, or `<nav>` (Web SDK only)

If the parent DOM element does not meet any of the above criteria, the search continues recursively up the DOM hierarchy. If no matching elements are found, the value `BODY` is returned.

## Dimension items

Dimension items include regions that you have labeled on your site. Specific region values depend on what attributes are used, and if semantic HTML elements are present.
