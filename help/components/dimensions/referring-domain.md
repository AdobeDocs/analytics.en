---
title: Referring domain
description: The overarching domain a visitor was on before clicking through to your site.
---

# Referring domain

The 'Referring domain' dimension reports which domains visitors click through to reach your site. This dimension is useful to understand which third-party sites drive the most traffic to yours. A link must exist on the external site and a visitor must click it in order for the dimension value to show up.

>[!IMPORTANT] You must configure your report suite's [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) to use this dimension. Failure to configure internal URL filters can either include internal domains or prevent external domains from appearing.

## Populate this dimension with data

This dimension requires configuration in both the Analytics interface and your implementation.

* Within your implementation, this dimension retrieves data from the [`r` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `document.referrer` in the browser. If you use an AppMeasurement library (such as through Adobe Experience Platform Launch), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `r` query string parameter in image requests.
* Within the Analytics interface, you must configure your report suite's [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md). Failure to configure internal URL filters can either include internal domains or prevent external domains from appearing.

Adobe persists referring domain for a visit. If a visitor leaves and clicks through a link on a different domain within a single visit, the new value updates and persists for the remainder of the visit. If you only want to see the original value, see [Original referring domain](original-referring-domain.md).

## Dimension values

Dimension values include domains that visitors click through to your site. If a hit does not have any referrer data (either set or persisted), it groups under the dimension value `"Typed/Bookmarked"`. This dimension value means that there was no referrer value, such as if the visitor manually typed the browser address into the address bar, or clicked a bookmark.
