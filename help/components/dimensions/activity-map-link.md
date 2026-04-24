---
description: The link name that was clicked.
title: Activity Map Link
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
TQID: https://experienceleague.adobe.com/A5HaPb0TghRKVykJ9V2UMJ0mlsYElLkCyBwxzTd6VII
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
# Activity Map Link

The 'Activity Map Link' [dimension](overview.md) displays the most popular links that were clicked. You can use this dimension to compare which links on your site are used the most, regardless of where the links were clicked.

## Populate this dimension with data

This dimension retrieves data from the [Context data variable](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`. If your implementation uses [Activity Map](/help/analyze/activity-map/overview.md), this context data variable automatically collects data when links are clicked.

For a given link that was clicked, Activity Map searches for the following (in order):

1. The `s_objectID` variable
1. The link's inner text
1. The `alt` attribute for images
1. The `title` attribute
1. The `src` attribute for images
1. The `action` attribute for forms

If the clicked element contains none of the above criteria, Activity Map does not collect data for that click.

## Dimension items

Dimension items include the link text or other link attributes that visitors click. Your organization's site structure and implementation determines the exact values collected.
