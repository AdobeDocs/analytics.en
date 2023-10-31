---
title: Component support in Data Warehouse
description: Learn what additional dimensions and metrics are available in Data Warehouse and what is not supported.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
---
# Component support in Data Warehouse

The unique processing in Data Warehouse architecture allows some components that aren't typically available in other capabilities of Adobe Analytics. Due to its unique architecture, some components are not available for use in either reports or segments. Use this page to understand what can be used, and what cannot.

## Components unique to Data Warehouse

Some dimensions and metrics that can be used in Data Warehouse are not available when using other capabilities in Adobe Analytics.

### Dimensions supported exclusively

* **Experience Cloud ID**: For implementations that use the Experience Cloud ID Service (ECID), a 128-bit number consisting of two concatenated 64-bit numbers padded to 19 digits.
* **Page URL**: The page URL the hit occurred on.
* **Purchase IDs**: Unique identifier for a purchase, set using the purchaseID variable.
* **Visitor ID**: Provides the unique identifier for the visitor. This value is the same as concatenated value of `visid_high` and `visid_low` columns in data feeds. See [Data column reference](../analytics-data-feed/c-df-contents/datafeeds-reference.md) under Data Feeds for more information.

### Metrics supported exclusively

* **Visits**: This metric in context of Data Warehouse excludes non-persistent cookie visits.
* **Visits - All Visitors**: This metric in context of Data Warehouse has closer parity with the visits metric in other tools within Adobe Analytics.

## Components not supported in Data Warehouse

Some dimensions and metrics are not supported in Data Warehouse.

>[!NOTE]
>
>If a dimension or metric is not supported in Data Warehouse, segments using these components are not supported either. Always check product compatibility when creating or editing a segment.

### Dimensions not supported

* AM/PM 
* Some pathing-based dimensions, including:
  * All Entry dimensions, except Entry Page
  * All Exit dimensions, except Exit Page and Exit Link
  * Hit Depth
  * Return Frequency
  * Time Prior to Event
  * Time Spent on Page - Bucketed
  * Time Spent per Visit - Bucketed
* All Search Page Rank
* Hierarchy variables
* Hit Type
* Pages not Found (available as a dimension; not supported for segmentation)
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
  * 'Time Spent' metrics 
* Participation metrics (as described in [Build a "Participation" metric](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md))
   
### Dimensions supported in a different way

The following time-based dimensions are supported. However, the output of dates is non-standard when using these dimensions. Specifically, the year is offset by 1900, and months are zero-based.

* Year
* Quarter
* Month
* Week
* Day
* Hour
* Minute
