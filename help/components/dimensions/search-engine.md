---
title: Search engine
description: The search engine that the visitor used to reach your site.
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
---
# Search engine

The 'Search engine' dimension reports the search engines that visitors use to reach your site. A referrer must meet both of the following to classify as a search engine:

* The referring domain is recognized by Adobe as a valid search engine;
* A keyword query string parameter exists in the referring URL. The query string parameter can be blank (as is the case with several search engines due to privacy practices).

If you want to distinguish paid and natural search, [Paid search detection](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md) is required. Multiple dimensions are available for search engines:

* **Search engine**: The search engine used to reach your site, regardless of if it is paid or natural.
* **Search engine - paid**: The search engine used to reach your site, which matched paid search detection.
* **Search engine - natural**: The search engine used to reach your site, which did not match paid search detection.

## Populate this dimension with data

This dimension references multiple lookup tables internal to Adobe. Each value is based on the [referrer](referrer.md) of the hit, which depends on [Internal URL filters](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). Make sure that the referrer dimension and internal URL filters are configured correctly.

## Dimension items

Dimension items include search engines used to reach your site. Example values include `"Google"`, `"Microsoft Bing"`, and `"DuckDuckGo"`. The `"Unspecified"` dimension item is all non-search traffic.
