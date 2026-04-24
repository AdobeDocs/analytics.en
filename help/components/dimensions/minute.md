---
title: Minute
description: The minute that the metric occurred on.
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
TQID: https://experienceleague.adobe.com/GRivRprXBteGxRZieSI3uyjHALDJ-0hHbZx3S9ldJW0
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Minute

The 'Minute' [dimension](overview.md) reports the minute that a given metric occurred (rounded down). The first dimension item is the first minute in the date range, and the last dimension item is the last minute in the date range. This dimension is valuable for trended reports, as it allows you to see metrics over time. Given how granular this dimension is, Adobe recommends limiting the reporting date range to one or two days.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include a given minute within a report's date range alongside its date. It is formatted as `HH:MM YYYY-MM-DD`. Dimension items starting with `00:00` equate to midnight on that day, while values starting with `23:59` equate to 11:59 PM for that day.
