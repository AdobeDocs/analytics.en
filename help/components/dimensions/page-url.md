---
title: Page URL
description: The URL of the page.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
---
# Page URL

The 'Page URL' dimension lists the URLs on your site.

>[!IMPORTANT]
>
>This dimension is only available in Data Warehouse. If you want to use a URL dimension in other Analytics solutions, consider copying the value into an [eVar](evar.md) on every hit.

## Populate this dimension with data

This dimension retrieves data from the [`g` and `-g` query strings](/help/implement/validate/query-parameters.md) in [Page view calls (`t()`)](/help/implement/vars/functions/t-method.md). [Link tracking calls (`tl()`)](/help/implement/vars/functions/tl-method.md) always strip this dimension, even if the `g` query string exists.

Sometimes URLs are longer than 255 bytes. AppMeasurement uses the `g` query string parameter for the first 255 bytes of the URL in image requests. If a URL is longer than 255 bytes, the rest of the URL is stored in the `-g` query string parameter. Protocol and query strings in the URL are included in this variable.

AppMeasurement automatically collects this data based on the page's URL. You can override the collected value using the [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variable.

## Populate an eVar with URL

Adobe recommends setting an eVar to the concatenated string `window.location.hostname + window.location.pathname`. This string typically works better than `window.location.href` because it omits protocol, query strings, and anchor tags.

If you want the eVar to exactly match the 'Page URL' dimension in Data Warehouse, you can use [dynamic variables](/help/implement/vars/page-vars/dynamic-variables.md) and set the eVar to `D=g` on each hit.

## Dimension items

Dimension items include the URLs of pages on your site.
