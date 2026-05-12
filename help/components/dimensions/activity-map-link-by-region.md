---
title: Activity Map Link By Region
description: A concatenated value of link and region.
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
TQID: https://experienceleague.adobe.com/xvYVA064hA0rsBdnLpxXllq3PD0zYAikFRjc6xNErvg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
# Activity Map Link By Region

The 'Activity Map Link By Region' [dimension](overview.md) displays a concatenation of [Activity Map Link](activity-map-link.md) and [Activity Map Region](activity-map-link-by-region.md). This dimension is useful when you have links that are named similarly, but reside in different regions of your site. For example, if you have multiple links to your home page that are all labeled "Home", you can use this dimension to distinguish those links in each site region.

## Populate this dimension with data

This dimension retrieves data from the [Context data variables](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link` and `c.a.activitymap.region`. These two values are concatenated and separated by a pipe (`|`). If your implementation uses [Activity Map](/help/analyze/activity-map/overview.md), these context data variables automatically collect data when links are clicked.

## Dimension items

Dimension items include values from [Activity Map Link](activity-map-link.md) and [Activity Map Region](activity-map-link-by-region.md). Your organization's site structure and implementation determines the exact values collected.
