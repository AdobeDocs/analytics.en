---
title: Week
description: The week that the metric occurred on.
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
---
# Week

The 'Week' dimension reports the week that a given metric occurred. The first dimension item is the first week in the date range, and the last dimension item is the last week in the date range. This dimension is vital for trended reports, as it allows you to see metrics over time.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

In Analysis Workspace, dimension items include the date (month, day, and year) of the first day of the week.

In Data Warehouse, dimension items include numbered weeks based on the request's date range. For example, the first full week is `"Week 1"`. If a request includes a partial week, data is grouped into the dimension item `"Week 0"`.
