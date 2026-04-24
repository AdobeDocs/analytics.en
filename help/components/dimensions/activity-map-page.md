---
title: Activity Map Page
description: The page name when a link was clicked.
feature: Dimensions
role: User, Admin
exl-id: 8dc5d5a1-ee44-4c98-80fa-13dd1cf4edf2
TQID: https://experienceleague.adobe.com/WJ0uk-LqIABwehzzy79c2o1cd3EvI-AKUJ--vmLnKRE
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
# Activity Map Page

The 'Activity Map Page' [dimension](overview.md) displays the page that a visitor was on when a link was clicked. You can use this dimension to determine what pages contain links that get clicked on the most. This dimension is also used by the Activity Map overlay to determine which links to display.

## Populate this dimension with data

This dimension retrieves data from the [Context data variable](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`. If your implementation uses [Activity Map](/help/analyze/activity-map/overview.md), this context data variable automatically collects data when links are clicked.

For a given link that was clicked, this context data variable collects the value in the [Page](page.md) dimension. If the Page dimension does not contain a value, the [Page URL](page-url.md) dimension is used instead (similarly to the fallback that the Page dimension uses). Activity Map data is typically sent on the next hit after a link was clicked. This dimension allows you to determine the page value when the link was clicked, instead of the page value when data was sent.

## Dimension items

Dimension items include all values found in the [Page](page.md) dimension.
