---
title: Component support in Data Warehouse
description: Learn what additional dimensions and metrics are available in Data Warehouse and what is not supported.
---

# Component support in Data Warehouse

Data Warehouse's unique processing architecture allows some components that aren't typically available in other capabilities of Adobe Analytics. Also due to its unique architecture, some components are not available for use in either reports or segments. Use this page to understand what can be used, and what cannot.

## Components unique to Data Warehouse

Some dimensions and metrics can be used in Data Warehouse whereas they are not available using other capabilities in Adobe Analytics.

### Dimensions supported exclusively

* Experience Cloud Visitor ID:
* IP:
* Page URL:
* Purchase IDs:
* Visitor ID: Provides the unique identifier for the visitor. This value is the same as concatenated value of `visid_high` and `visid_low` columns in data feeds. See [Data column reference](../analytics-data-feed/c-df-contents/datafeeds-reference.md) under Data Feeds for more information.

### Metrics supported exclusively

* Visits: This metric in context of Data Warehouse exclude non-persistent cookie visits.
* Visits - All Visitors: This metric in context of Data Warehouse has closer parity with the visits metric in other tools within Adobe Analytics.

## Components not supported in Data Warehouse

Some dimensions and metrics are not supported in Data Warehouse.

> [!IMPORTANT] If a dimension or metric is not supported in Data Warehouse, segments using these components are not supported either. Always check product compatibility when creating or editing a segment.

### Dimensions not supported

* Some time-based dimensions, including:
  * AM/PM
  * Day of Month
  * Day of Week
  * Day of Year
  * Hour of Day
  * Minute
  * Month of Year
  * Quarter of Year
  * Weekday/Weekend
  * Year
* Some pathing-based dimensions, including:
  * All Entry dimensions, except Entry Page
  * All Exit dimensions, except Exit Page and Exit Link
  * Hit Depth
  * Return Frequency
  * Time Prior to Event
  * Time Spent on Page - Bucketed
  * Time Spent per Visit - Bucketed
  * Visit Depth
* All Search Page Rank
* Hierarchy variables
* Hit Type
* Pages not Found (segments only)
* Paid Search
* Single Page Visits
* Tracking Opt-out Reason
* US States

### Metrics not supported

* Some pathing-based metrics, including:
  * Bounces
  * Entries
  * Exits
  * Reloads
  * Single Access
  * Time Spent metrics
