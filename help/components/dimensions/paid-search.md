---
title: Paid search
description: Distinguishes metrics from paid and natural search.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
---
# Paid search

The 'Paid search' dimension lets you look at any metric and compare it between paid search and natural search. All other hits outside search engines are omitted. This dimension is helpful to understand how your paid search efforts compare with organic search.

## Populate this dimension with data

The only requirement for this dimension to work properly is to have [Paid search detection](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.mdd) configured correctly in report suite settings. If paid search detection is configured correctly and a report suite has data, this dimension always works.

## Dimension items

Dimension items include two static values: `"Natural"` and `"Paid"`. If a visit matches criteria for a search engine and also matches paid search detection, it belongs to the `"Paid"` dimension item. If a visit matches criteria for a search engine and does *not* match paid search detection, it belongs to the `"Natural"` dimension item.
