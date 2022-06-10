---
title: Original referring domain
description: The first referring domain a visitor was on before clicking through to your site.
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
---
# Original referring domain

The 'Original referring domain' dimension reports the first referring domain that a visitor clicked through to reach your site. Once it is set, it contains the same value for the entire lifetime of that visitor ID. This dimension is useful to understand which third-party sites originally drive traffic to your site.

>[!IMPORTANT]
>
>You must configure your report suite's [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) to use this dimension. Failure to configure internal URL filters can either include internal domains or prevent external domains from appearing.

## Populate this dimension with data

This dimension requires configuration in both the Analytics interface and your implementation.

* Within your implementation, this dimension retrieves data from the [`r` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `document.referrer` in the browser. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `r` query string parameter in image requests.
* Within the Analytics interface, you must configure your report suite's [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md). Failure to configure internal URL filters can either include internal domains or prevent external domains from appearing.

Adobe persists original referring domain for a visitor's lifetime. If a visitor leaves and clicks through a link on a different domain at any time, the new value is not recorded. If you want to see new values, see [Referring domain](referring-domain.md).

## Dimension items

Dimension items include domains that visitors click through to your site. If a hit does not have any referrer data (either set or persisted), it groups under the dimension item `"None"`. This dimension item means that there was no referrer value, such as if the visitor manually typed the browser address into the address bar, or clicked a bookmark.

## Compare Referring domain to Original referring domain

Referring domain can change between visits. For example, a visitor arrives to your site through `google.com`, then a week later, arrives to your site through `twitter.com`. Eventually they make a purchase on your site. If using Referring domain as the dimension with last touch attribution, `twitter.com` gets credit for the purchase. If using Original referring domain as the dimension, `google.com` gets credit for the purchase regardless of attribution model.

Original referring domain never changes for the entire lifetime of a given visitor ID.
