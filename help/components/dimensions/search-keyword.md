---
title: Search keyword
description: The search keyword that the visitor used to reach your site.
feature: Dimensions
exl-id: 5a1236a6-f94b-4679-906a-b539afe36887
---
# Search keyword

The 'Search keyword' dimension reports the search keywords that visitors use to reach your site.

>[!IMPORTANT]
>
>Most search engines no longer pass the search keyword due to increasing privacy practices. Hits where Adobe recognizes a search engine but is missing a keyword groups under the dimension item `"Keyword unavailable"`.

A referrer must meet both of the following to classify as a search keyword:

* The referring domain is recognized by Adobe as a valid [Search engine](search-engine.md);
* A keyword query string parameter exists in the referring URL. If the keyword query string exists but does not contain a value, it groups under the dimension item `"Keyword unavailable"`.

If you want to distinguish paid and natural search, [Paid search detection](/help/admin/admin/paid-search-detection/paid-search-detection.md) is required. Multiple dimensions are available for search keywords:

* **Search keyword**: The search keyword used to reach your site, regardless of if it is paid or natural.
* **Search keyword - paid**: The search keyword used to reach your site, which matched paid search detection.
* **Search keyword - natural**: The search keyword used to reach your site, which did not match paid search detection.

## Populate this dimension with data

This dimension references multiple lookup tables internal to Adobe. Each value is based on the [referrer](referrer.md) of the hit, which depends on [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md). Make sure that the referrer dimension and internal URL filters are configured correctly.

## Dimension items

Dimension items include search keywords used to reach your site. The `"Unspecified"` dimension item is all non-search traffic.
