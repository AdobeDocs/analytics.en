---
title: Data Warehouse FAQ
description: Frequently asked questions for Data Warehouse.
feature: Data Warehouse
exl-id: 51c3ba17-a8b2-4030-9521-355ebbbfcd0d
---
# Data Warehouse FAQ

Frequently asked questions for Data Warehouse.

## When I use the granularity dropdown while creating a request, what format can I expect the dates to be in?

When applying granularity in a Data Warehouse request, the 'Date' column is added to the report. Depending on the granularity selected, the date format changes.

| Granularity | Format | Example |
| --- | --- | --- |
| Hourly | `mmmm d, yyyy` Hour `H` | January 1, 20XX, Hour 0 |
| Daily | `mmmm d, yyyy` | January 1, 20XX |
| Weekly | Week `w, yyyy` | Week 1, 20XX |
| Monthly | `mmmm yyyy` | January 20XX |
| Quarterly | `q` Quarter `yyyy` | 1st Quarter 20XX |
| Yearly | `yyyy` | 20XX |

## How do segments as dimensions work in Data Warehouse?

When you use a segment as a dimension in Data Warehouse, the report returns a column containing `"0"` or `"1"`:

* **`"0"`**: The dimension item did not meet the segment's criteria.
* **`"1"`**: The dimension item met the segment's criteria.
