---
title: Week
description: The week that the metric occurred on.
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
TQID: https://experienceleague.adobe.com/Vvr0Svg2khSzWbtWR5hLfveyctOEM-62WU6oxIsvzXs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
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
# Week

The 'Week' [dimension](overview.md) reports the week that a given metric occurred. The first dimension item is the first week in the date range, and the last dimension item is the last week in the date range. This dimension is vital for trended reports, as it allows you to see metrics over time.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

In Analysis Workspace, dimension items include the date (month, day, and year) of the first day of the week.

In Data Warehouse, dimension items include numbered weeks based on the request's date range. For example, the first full week is `"Week 1"`. If a request includes a partial week, data is grouped into the dimension item `"Week 0"`.
