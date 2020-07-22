---
title: Hour of day
description: The numeric hour of the day, regardless of which day.
---

# Hour of day

The 'Hour of day' dimension reports the numeric hour of any given day as a dimension item. For example, if you have a report spanning January 1 - January 7, the first hour of each day groups into the same dimension item. This report is valuable if you want a report broken out by relative time of day, but do not want a static hours as dimension items. It is especially valuable as a dimension in scheduled reports, as this dimension rolls with the selected date range.

This dimension is based on the report suite's time zone, and not the visitor's local time zone. For example, if your report suite is in Mountain time and a visitor in California visits your site at 10:00 AM Pacific time, the hit groups under the `11:00 AM` dimension item. If you want a dimension that records the local visitor's time, Adobe recommends using the [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) plug-in.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include `12:00 AM` - `11:00 PM`, representing the hour of the day that the hit occurred on (rounded down). For example, if a hit was generated at 3:58 PM, it groups under the dimension item of `3:00 PM`.
