---
title: Activity Map Page
description:
feature: Dimensions
---
# Activity Map Page

The 'Activity Map Page' [dimension](overview.md) displays what pages a visitor was on when a link was clicked. You can use this dimension to determine what pages contain links that get clicked on the most. This dimension is also used by the Activity Map overlay to determine which links to display.

## Populate this dimension with data

This dimension retrieves data from the [Context data variable](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`. If your implementation uses [Activity Map](/help/analyze/activity-map/overview.md), this context data variable automatically collects data when links are clicked.

For a given link that was clicked, this context variable collects the value in the [Page](page.md) dimension. Since Activity Map data is sent on the next hit after a link was clicked, the value in this dimension ends up being the previous page.

## Dimension items

Dimension items include all values found in the [Page](page.md) dimension.
