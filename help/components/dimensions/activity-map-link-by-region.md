---
title: Activity Map Link By Region
description: A concatenated value of link and region.
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
---
# Activity Map Link By Region

The 'Activity Map Link By Region' [dimension](overview.md) displays a concatenation of [Activity Map Link](activity-map-link.md) and [Activity Map Region](activity-map-link-by-region.md). This dimension is useful when you have links that are named similarly, but reside in different regions of your site. For example, if you have multiple links to your home page that are all labeled "Home", you can use this dimension to distinguish those links in each site region.

## Populate this dimension with data

This dimension retrieves data from the [Context data variables](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link` and `c.a.activitymap.region`. These two values are concatenated and separated by a pipe (`|`). If your implementation uses [Activity Map](/help/analyze/activity-map/overview.md), these context data variables automatically collect data when links are clicked.

## Dimension items

Dimension items include values from [Activity Map Link](activity-map-link.md) and [Activity Map Region](activity-map-link-by-region.md). Your organization's site structure and implementation determines the exact values collected.
