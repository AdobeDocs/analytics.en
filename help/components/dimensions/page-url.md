---
title: Page URL
description: The URL of the page.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Page URL

The 'Page URL' [dimension](overview.md) lists the URLs on your site.

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
