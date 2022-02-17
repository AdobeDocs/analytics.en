---
title: Pages not found
description: URLs that returned an error on your site.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
---
# Pages not found

*This help page describes how 'Pages not found' works as a dimension. See the [Pages not found](../metrics/pages-not-found.md) metric for more information.*

The 'Pages not found' dimension shows URLs that contained an error. This dimension is useful when you want to lower the number of errors that visitor get on your site.

* You can use this dimension in a [Flow visualization](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) to see which pages visitors click through to reach the error. You can then work with development teams in your organization to fix the link on each page.
* You can use this dimension with the ['Referrer'](referrer.md) dimension to see where visitors arrive to your site from external links. You can then either implement redirects to the desired location, or work with the third party to get the link fixed.

## Populate this dimension with data

This dimension retrieves data from the [`pageType` and `g` query strings](/help/implement/validate/query-parameters.md) in image requests. If the `pageType` query string equals `errorPage`, the `g` query string (page URL) is recorded. AppMeasurement collects this data using the [`pageType`](/help/implement/vars/page-vars/pagetype.md) variable. If the `pageType` variable is not defined or set to anything other than `errorPage`, no data for this dimension is collected.

## Dimension items

Dimension items include the URLs of pages on your site where an error occurred.
