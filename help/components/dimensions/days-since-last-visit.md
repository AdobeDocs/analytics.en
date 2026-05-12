---
title: Days since last visit
description: The number of days between the current hit and the last time they visited.
feature: Dimensions
exl-id: 8063bdc6-516a-4dd0-a4ca-ded739e8d406
TQID: https://experienceleague.adobe.com/VOkdvehFSgp1xBEq49W5FIphzHi8ZCbrsoMnI7rgQMs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
# Days since last visit

The 'Days since last visit' [dimension](overview.md) measures the amount of time passed between the current hit of the visitor and their previous visit (if there is one). This dimension helps you understand behavior visitors make after visiting your site. Examples include:

* How frequently do users revisit the site? 
* How does return frequency correlate with conversion? Do repeat buyers visit frequently or infrequently? 
* Do users who click through campaigns return frequently?

First-time visitors are not included in this dimension.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include the number of days between a visitor's last visit and the current hit. Each number of days is a separate dimension item, with `"Same day"` occurring where a visitor's last visit and the current hit happened on the same day.
