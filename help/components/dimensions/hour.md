---
title: Hour
description: The hour that the metric occurred on.
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
---
# Hour

The 'Hour' dimension reports the hour that a given metric occurred (rounded down). The first dimension item is the first hour in the date range, and the last dimension item is the last hour in the date range. This dimension is valuable for trended reports, as it allows you to see metrics over time.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include a given hour within a report's date range alongside its date. It is formatted as `HH:HH YYYY-MM-DD`.

## Daylight Savings Time

Daylight Savings Time is a practice where clocks are set an hour ahead in the spring, and set back an hour in the fall. If a report suite's time zone uses DST, Adobe adjusts data accordingly for that hour.

* **When Daylight Savings Time begins**: In March, reports typically show an hour gap in data where Daylight Savings Time starts. The hour did not exist, so it is not part of data collection. Note that a small amount of data can still make it into this hour. Adobe data collection servers take several seconds (up to a minute) to take DST adjustments into account.
* **When Daylight Savings Time ends**: In November, reports typically show a double-stacked hour where Daylight Savings Time ends. The hour happened twice, so both hours are aggregated in reports.
