---
title: Revenue
description: The monetary amount of products purchased within all orders.
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
---
# Revenue

The 'Revenue' metric shows the monetary amount of products purchased within all orders. This metric is vital for eCommerce sites in measuring conversion. You can combine this metric with any dimension to see what which dimension items contributed to revenue. For example, you could see the top campaigns (using the [Tracking code](../dimensions/tracking-code.md) dimension) or top internal search terms (using an [eVar](../dimensions/evar.md)).

## How this metric is calculated

For every hit where `purchase` exists in the [`events`](/help/implement/vars/page-vars/events/event-purchase.md) variable, sum the 'Price' field within the [`products`](/help/implement/vars/page-vars/products.md) variable.

This metric relies on the [currencyCode](/help/implement/vars/config-vars/currencycode.md) variable if the currency on the page is different than the report suite's native currency.
