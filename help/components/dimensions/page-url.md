---
title: Page URL
description: The URL of the page.
---

# Page URL

The 'Page URL' dimension lists the URLs on your site.

>[!IMPORTANT]
>
>This dimension is only available in Data Warehouse. If you want to use a URL dimension in other Analytics solutions, use an [eVar](evar.md).

## Populate this dimension with data

This dimension retrieves data from the [`g` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variable.

## Populate an eVar with URL

Adobe recommends setting an eVar to the concatenated string `window.location.hostname + window.location.pathname`. This string typically works better than `window.location.href` because it omits protocol, query strings, and anchor tags.

If you want the eVar to exactly match the 'Page URL' dimension in Data Warehouse, you can use [dynamic variables](/help/implement/vars/page-vars/dynamic-variables.md) and set the eVar to `D=g` on each hit. Note that this method does not work for custom link hits, as the page URL is stripped for all [`tl()`](/help/implement/vars/functions/tl-method.md) calls.

## Dimension items

Dimension items include the URLs of pages on your site.
