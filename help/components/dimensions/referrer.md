---
title: Referrer
description: The URL a visitor was at before clicking through to your site.
---

# Referrer

The 'Referrer' dimension reports which URLs visitors were on when clicking through to reach your site. This dimension is useful to understand which specific URLs drive the most traffic to your site. A link must exist on the external URL and a visitor must click it in order for the dimension value to show up.

>[!IMPORTANT] You must configure your report suite's [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) to use this dimension. Failure to configure internal URL filters can either include internal URLs or prevent external URLs from appearing.

## Populate this dimension with data

This dimension requires configuration in both the Analytics interface and your implementation.

* Within your implementation, this dimension retrieves data from the [`r` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `document.referrer` in the browser. If you use an AppMeasurement library (such as through Adobe Experience Platform Launch), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `r` query string parameter in image requests.
* Within the Analytics interface, you must configure your report suite's [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md). Failure to configure internal URL filters can either include internal URLs or prevent external URLs from appearing.

## Dimension values

Dimension values include URLs that visitors click through to your site. If a hit does not have any referrer data, it groups under the dimension value `"Typed/Bookmarked"`. This dimension value means that there was no referrer value, such as if the visitor manually typed the browser address into the address bar, or clicked a bookmark.
