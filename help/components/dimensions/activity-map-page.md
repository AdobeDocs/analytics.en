---
title: Activity Map Page
description: The page name when a link was clicked.
feature: Dimensions
role: User, Admin
---
# Activity Map Page

The 'Activity Map Page' [dimension](overview.md) displays the page that a visitor was on when a link was clicked. You can use this dimension to determine what pages contain links that get clicked on the most. This dimension is also used by the Activity Map overlay to determine which links to display.

## Populate this dimension with data

This dimension retrieves data from the [Context data variable](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`. If your implementation uses [Activity Map](/help/analyze/activity-map/overview.md), this context data variable automatically collects data when links are clicked.

For a given link that was clicked, this context data variable collects the value in the [Page](page.md) dimension. If the Page dimension does not contain a value, the [Page URL](page-url.md) dimension is used instead (similarly to the fallback that the Page dimension uses). Activity Map data is typically sent on the next hit after a link was clicked. This dimension allows you to determine the page value when the link was clicked, instead of the page value when data was sent.

## Dimension items

Dimension items include all values found in the [Page](page.md) dimension.
