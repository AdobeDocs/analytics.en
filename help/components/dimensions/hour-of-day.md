---
title: Hour of day
description: The numeric hour of the day, regardless of which day.
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
TQID: https://experienceleague.adobe.com/cktusukSxy7fHIIUi-7MSmx8Gl9FlUObfmJGS3VC3Jw
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
# Hour of day

The 'Hour of day' [dimension](overview.md) reports the numeric hour of any given day as a dimension item. For example, if you have a report spanning January 1 - January 7, the first hour of each day groups into the same dimension item. This report is valuable if you want a report broken out by relative time of day, but do not want a static hours as dimension items. It is especially valuable as a dimension in scheduled reports, as this dimension rolls with the selected date range.

This dimension is based on the report suite's time zone, and not the visitor's local time zone. For example, if your report suite is in Mountain time and a visitor in California visits your site at 10:00 AM Pacific time, the hit groups under the `11:00 AM` dimension item. If you want a dimension that records the local visitor's time, Adobe recommends using the [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) plug-in.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include `12:00 AM` - `11:00 PM`, representing the hour of the day that the hit occurred on (rounded down). For example, if a hit was generated at 3:58 PM, it groups under the dimension item of `3:00 PM`.

## Daylight Savings Time

Daylight Savings Time is a practice where clocks are set an hour ahead in the spring, and set back an hour in the fall. If a report suite's time zone uses DST, Adobe adjusts data accordingly for that hour.

* **When Daylight Savings Time begins**: In March, reports typically show an hour gap in data where Daylight Savings Time starts. The hour did not exist, so it is not part of data collection. Note that a small amount of data can still make it into this hour. Adobe data collection servers take several seconds (up to a minute) to take DST adjustments into account.
* **When Daylight Savings Time ends**: In November, reports typically show a double-stacked hour where Daylight Savings Time ends. The hour happened twice, so both hours are aggregated in reports.
