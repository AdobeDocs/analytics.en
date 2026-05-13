---
title: Day of month
description: The numeric day of the month, regardless of which month.
feature: Dimensions
exl-id: 6d27aa9f-ce75-4a27-bb92-3acabe3975a1
TQID: https://experienceleague.adobe.com/jSrKlf4a5f-6MTrQwwUcvRJep4chAUyOsj5hFjE1HRg
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
# Day of month

The 'Day of month' [dimension](overview.md) reports the numeric day of any given month as a dimension item. For example, if you have a report spanning January 1 - March 31, the first of each month groups into the same dimension item. This report is valuable if you want a report broken out by day, but do not want a static date as dimension items. It is especially valuable as a dimension in scheduled reports, as this dimension rolls with the selected date range.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include the numbers `1` - `31`, representing the day of the month that the hit occurred on.
