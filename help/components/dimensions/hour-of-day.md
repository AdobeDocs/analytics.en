---
title: Hour of day
description: The numeric hour of the day, regardless of which day.
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
---
# Hour of day

The 'Hour of day' dimension reports the numeric hour of any given day as a dimension item. For example, if you have a report spanning January 1 - January 7, the first hour of each day groups into the same dimension item. This report is valuable if you want a report broken out by relative time of day, but do not want a static hours as dimension items. It is especially valuable as a dimension in scheduled reports, as this dimension rolls with the selected date range.

This dimension is based on the report suite's time zone, and not the visitor's local time zone. For example, if your report suite is in Mountain time and a visitor in California visits your site at 10:00 AM Pacific time, the hit groups under the `11:00 AM` dimension item. If you want a dimension that records the local visitor's time, Adobe recommends using the [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) plug-in.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include `12:00 AM` - `11:00 PM`, representing the hour of the day that the hit occurred on (rounded down). For example, if a hit was generated at 3:58 PM, it groups under the dimension item of `3:00 PM`.

## Daylight Savings Time

Daylight Savings Time is a practice where clocks are set an hour ahead in the spring, and set back an hour in the fall. If a report suite's time zone uses DST, Adobe adjusts data accordingly for that hour.

* **When Daylight Savings Time begins**: In March, reports typically show an hour gap in data where Daylight Savings Time starts. The hour did not exist, so it is not part of data collection. Note that a small amount of data can still make it into this hour. Adobe data collection servers take several seconds (up to a minute) to take DST adjustments into account.
* **When Daylight Savings Time ends**: In November, reports typically show a double-stacked hour where Daylight Savings Time ends. The hour happened twice, so both hours are aggregated in reports.
