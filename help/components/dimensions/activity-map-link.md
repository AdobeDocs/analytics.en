---
description: The link name that was clicked.
title: Activity Map Link
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
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
