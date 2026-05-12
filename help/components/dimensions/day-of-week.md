---
title: Day of week
description: The day of the week, regardless of date range.
feature: Dimensions
exl-id: 01aa6b5f-49e6-4f86-97c7-8d0ff431e15b
TQID: https://experienceleague.adobe.com/9nudTrYTDMEFXSo81uUuw9KFT3mRPhZer3cX81AwoPM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
# Day of week

The 'Day of week' [dimension](overview.md) reports the day of the week the hit occurred. This report is valuable if you want a report broken out by week, but do not want a static days as dimension items. It is especially valuable as a dimension in scheduled reports, as this dimension works with any date range.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include `Sunday` - `Saturday`, representing the day of the week that the hit occurred on. The order of dimension items respects the first day of the week in [Customize calendar](/help/admin/tools/manage-rs/edit-settings/general/custom-calendar.md) by default.
