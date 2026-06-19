---
title: Component Support in Data Warehouse
description: Learn which dimensions and metrics are available when you build a Data Warehouse request, which are unavailable, and which behave differently.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
TQID: https://experienceleague.adobe.com/NhSEyPN3093B9M0SngJluJdZScI2lXvRyHkXQd8gg-4
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
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Component support in Data Warehouse

This page describes the dimensions and metrics you can use when building a Data Warehouse request. Sections include which components are available, which are unavailable, and which behave differently than in other Adobe Analytics tools.

## Dimensions exclusive to Data Warehouse

The following dimensions can be used in Data Warehouse but are not available in other Adobe Analytics capabilities.

* [[!UICONTROL Experience Cloud Visitor ID]](/help/components/dimensions/experience-cloud-visitor-id.md)
* [[!UICONTROL IP Address]](/help/components/dimensions/ip-address.md)
* [[!UICONTROL Page URL]](/help/components/dimensions/page-url.md)
* [[!UICONTROL Purchase ID]](/help/components/dimensions/purchase-id.md)
* [[!UICONTROL Visitor ID]](/help/components/dimensions/visitor-id.md)

## Dimensions not supported

The following dimensions are not available in Data Warehouse reports or segments:

* [[!UICONTROL AM/PM]](/help/components/dimensions/am-pm.md)
* All entry dimensions, except [[!UICONTROL Entry Page]](/help/components/dimensions/entry-dimensions.md) and [[!UICONTROL Entry page original]](/help/components/dimensions/entry-dimensions.md) which are allowed
* All exit dimensions, except [[!UICONTROL Exit Page]](/help/components/dimensions/exit-dimensions.md) and [[!UICONTROL Exit Link]](/help/components/dimensions/exit-link.md) which are allowed
* [[!UICONTROL Hit Depth]](/help/components/dimensions/hit-depth.md)
* [[!UICONTROL Return Frequency]](/help/components/dimensions/return-frequency.md)
* [[!UICONTROL Time Prior to Event]](/help/components/dimensions/time-prior-to-event.md)
* [[!UICONTROL Time Spent on Page - Bucketed]](/help/components/dimensions/time-spent-on-page.md)
* [[!UICONTROL Time Spent per Visit - Bucketed]](/help/components/dimensions/time-spent-per-visit.md)
* [[!UICONTROL All Search Page Rank]](/help/components/dimensions/all-search-page-rank.md)
* [[!UICONTROL Hierarchy]](/help/components/dimensions/overview.md#retired-dimensions) variables
* [[!UICONTROL Hit Type]](/help/components/dimensions/hit-type.md)
* [[!UICONTROL Paid Search]](/help/components/dimensions/paid-search.md)
* [[!UICONTROL Single Page Visits]](/help/components/dimensions/single-page-visits.md)
* [[!UICONTROL Tracking Opt-out Reason]](/help/components/dimensions/tracking-opt-out-reason.md)
* [[!UICONTROL US States]](/help/components/dimensions/us-states.md)

Some dimensions are available in a Data Warehouse request but cannot be used inside a segment. See [Data Warehouse segment compatibility](segment-compatibility.md) for more information.

## Dimensions with non-standard date formatting

The following time-based dimensions are supported in Data Warehouse reports, but their output uses a non-standard format:

* [[!UICONTROL Year]](/help/components/dimensions/year.md)
* [[!UICONTROL Quarter]](/help/components/dimensions/quarter.md)
* [[!UICONTROL Month]](/help/components/dimensions/month.md)
* [[!UICONTROL Week]](/help/components/dimensions/week.md)
* [[!UICONTROL Day]](/help/components/dimensions/day.md)
* [[!UICONTROL Hour]](/help/components/dimensions/hour.md)
* [[!UICONTROL Minute]](/help/components/dimensions/minute.md)

Date values are output in the format `1YYMMDDHHMM`:

* **Year (YY)**: Offset by 1900. Add `1900` to the first three digits. For example, `125` = year **2025**.
* **Month**: Zero-based. January = `00`, February = `01`, ..., December = `11`.

For example, if the Date Range Week field shows `1260901`, the year is 1900 + 126 = **2026** and the month is 09 = **October**.

## Metrics defined differently in Data Warehouse

* **[[!UICONTROL Visits]](/help/components/metrics/visits.md)**: Excludes non-persistent cookie visits, unlike the Visits metric in other Adobe Analytics tools.
* **[[!UICONTROL Visits - All Visitors]](/help/components/metrics/visits.md)**: Counts all visitors including those with non-persistent cookies, making it the closer equivalent to the standard [!UICONTROL Visits] metric used elsewhere in Adobe Analytics.

## Metrics not supported

The following metrics are not available in Data Warehouse:

* [[!UICONTROL Bounces]](/help/components/metrics/bounces.md)
* [[!UICONTROL Entries]](/help/components/metrics/entries.md)
* [[!UICONTROL Exits]](/help/components/metrics/exits.md)
* [[!UICONTROL Reloads]](/help/components/metrics/reloads.md)
* [[!UICONTROL Single Access]](/help/components/metrics/single-access.md)
* Any [[!UICONTROL Time Spent]](/help/components/metrics/time-spent.md) metrics
* Any metrics using a [participation](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md) attribution model
