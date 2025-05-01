---
description: The available dimensions and metrics that you can read and write using processing rules.
subtopic: Processing rules
title: Dimensions available to processing rules
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
---
# Dimensions and metrics available to processing rules

The available dimensions and metrics that you can read and write using processing rules.

## Custom values and context data

| Value | Read/write status | Description |
| --- | --- | --- |
| Custom value | Read only | Custom text or values typed directly in the action of a processing rule. |
| Concatenated value | Read only | Values that are created by combining two values. For example, channel and page name can be combined to create a subcategory. |

## Hit attributes

| Attribute | Read/write status | Description |
| --- | --- | --- |
| Page URL | Read + write | The [Page URL](/help/components/dimensions/page-url.md) dimension. Link tracking hits strip this dimension before reaching processing rules. If you re-insert a page URL value using processing rules, the hit is considered a [Page view](/help/components/metrics/page-views.md) instead of a [Page event](/help/components/metrics/page-events.md). Adobe recommends checking for a value in the page dimension before modifying it. |
| Page name | Read + write | The [Page](/help/components/dimensions/page.md) dimension. Link tracking hits strip this dimension before reaching processing rules. If you re-insert a page value using processing rules, the hit is considered a [Page view](/help/components/metrics/page-views.md) instead of a [Page event](/help/components/metrics/page-events.md). Adobe recommends checking for a value in the page dimension before modifying it. |
| Report suite ID | Read only | The report suite that the processing rule is executed on. This report suite can be different than the report suite originally sent through AppMeasurement, such as when using VISTA rules. |
| AppMeasurement code version | Read only | The AppMeasurement library version used to generate the image request. |
| IP address | Read only | The IP address of the visitor. |
| User agent | Read only | The user agent of the visitor. |
| Referrer | Read only | The [Referrer](/help/components/dimensions/referrer.md) dimension. |
| Query string parameter | Read only | The value of a specified query string parameter in the current URL. |
| Referring query string parameter | Read only | The value of a specified query string parameter in the referring URL, or an empty string if none exists. |
| Referring domain | Read only | The page domain of the referring URL, including subdomains. |
| Referring root domain | Read only | The page domain of the referring URL, excluding subdomains. |
| Page query string | Read only | All query string parameters and their values in the current URL. |
| Referring query string | Read only | All query string parameters and their values in the referring URL. |
| Page path | Read only | The page path of the current URL. Page path does not include protocol, domain, or query string parameters. |
| Page domain | Read only | The page domain of the current URL, including subdomains. Page domain does not include page path or query string parameters. |
| Page root domain | Read only | The page domain of the current URL, excluding subdomains. |
| Customer perspective | Read + write | A flag that determines if the hit is a mobile background hit. |

## Conversion variables

| Variable | Read/write status | Description |
| --- | --- | --- |
| eVar 1-250 | Read + write | [eVar](/help/components/dimensions/evar.md) dimensions. |
| Campaign | Read + write | The [Tracking code](/help/components/dimensions/tracking-code.md) dimension. |
| Purchase ID | Read + write | The [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) implementation variable. |
| State | Read + write | The [`state`](/help/implement/vars/page-vars/state.md) implementation variable is retired. |
| Zip | Read + write | The [Zip code](/help/components/dimensions/zip-code.md) dimension. |
| Currency code | Read + write | The [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) implementation variable. IMPORTANT: If you set this variable to an invalid value, the hit is discarded. |
| Transaction ID | Read + write | The [`transactionID`](/help/import/data-sources/transactionid.md) implementation variable. |

>[!NOTE]
>Adobe does not support setting the [`products`](/help/implement/vars/page-vars/products.md) implementation variable using processing rules.

## Traffic variables

| Variable | Read/write status | Description |
| --- | --- | --- |
| Prop 1-75 | Read + write | [Prop](/help/components/dimensions/prop.md) dimensions. |
| Hierarchy 1-5 | Read + write | [Hierarchy](/help/components/dimensions/hierarchy.md) dimensions. |
| Server | Read + write | The [Server](/help/components/dimensions/server.md) dimension. |
| Channel | Read + write | The [Site section](/help/components/dimensions/site-section.md) dimension. |

## Context variables

All [Context data variables](/help/implement/vars/page-vars/contextdata.md) that this report suite has seen in previous image requests. If processing rules do not place context data into another variable, that data is permanently lost. See [Copy a context data variable to an eVar](processing-rules-examples/processing-rules-copy-context-data.md) and [Set an event using a context data variable](processing-rules-examples/processing-rules-copy-context-data-event.md) for usage examples.

## Success events

Processing rules can set events but cannot read them as conditions. Set the rule action drop-down to **[!UICONTROL Set event]** to see available metrics to increment.

| Variable | Read/write status | Description |
| --- | --- | --- |
| Orders | Write only | The [Orders](/help/components/metrics/orders.md) metric. |
| Carts | Write only | The [Carts](/help/components/metrics/carts.md) metric. |
| Cart views | Write only | The [Cart views](/help/components/metrics/cart-views.md) metric. |
| Checkouts | Write only | The [Checkouts](/help/components/metrics/checkouts.md) metric. |
| Cart additions | Write only | The [Cart additions](/help/components/metrics/cart-additions.md) metric. |
| Cart removals | Write only | The [Cart removals](/help/components/metrics/cart-removals.md) metric. |
| Event 1-1000 | Write only | [Custom events](/help/components/metrics/custom-events.md). |
| Product views | Write only | The [Product views](/help/components/metrics/product-views.md) metric. |

