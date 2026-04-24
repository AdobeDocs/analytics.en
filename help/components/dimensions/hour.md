---
title: Hour
description: The hour that the metric occurred on.
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
TQID: https://experienceleague.adobe.com/Gkigdxnrted-gkPoGCQMx229EvCmVvSt9Rr5QP-IfGU
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Hour

The 'Hour' [dimension](overview.md) reports the hour that a given metric occurred (rounded down). The first dimension item is the first hour in the date range, and the last dimension item is the last hour in the date range. This dimension is valuable for trended reports, as it allows you to see metrics over time.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include a given hour within a report's date range alongside its date. It is formatted as `HH:HH YYYY-MM-DD`.

## Daylight Savings Time

Daylight Savings Time is a practice where clocks are set an hour ahead in the spring, and set back an hour in the fall. If a report suite's time zone uses DST, Adobe adjusts data accordingly for that hour.

* **When Daylight Savings Time begins**: In March, reports typically show an hour gap in data where Daylight Savings Time starts. The hour did not exist, so it is not part of data collection. Note that a small amount of data can still make it into this hour. Adobe data collection servers take several seconds (up to a minute) to take DST adjustments into account.
* **When Daylight Savings Time ends**: In November, reports typically show a double-stacked hour where Daylight Savings Time ends. The hour happened twice, so both hours are aggregated in reports.
