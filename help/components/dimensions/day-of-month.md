---
title: Day of month
description: The numeric day of the month, regardless of which month.
feature: Dimensions
exl-id: 6d27aa9f-ce75-4a27-bb92-3acabe3975a1
---
# Day of month

The 'Day of month' dimension reports the numeric day of any given month as a dimension item. For example, if you have a report spanning January 1 - March 31, the first of each month groups into the same dimension item. This report is valuable if you want a report broken out by day, but do not want a static date as dimension items. It is especially valuable as a dimension in scheduled reports, as this dimension rolls with the selected date range.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include the numbers `1` - `31`, representing the day of the month that the hit occurred on.
