---
title: Units
description: The total number of products purchased within all orders.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
---
# Units

The 'Units' metric shows the total number of products purchased within all orders. This metric is vital for eCommerce sites in measuring conversion. You can combine this metric with any dimension to see what which dimension items contributed to how many products were purchased. For example, you could see the top campaigns (using the [Tracking code](../dimensions/tracking-code.md) dimension) or top internal search terms (using an [eVar](../dimensions/evar.md)) that contributed to products purchased.

## How this metric is calculated

For every hit where `purchase` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable, sum the 'Quantity' field within the [`products`](/help/implement/vars/page-vars/products.md) variable.

## Compare orders and units

The [Orders](orders.md) metric only records the number of purchase events. The 'Units' metric is typically higher than 'Orders' because customers can purchase more than one product. In these cases, a single order exists with multiple units.

If you have orders higher than units, Adobe recommends to check the integrity of your implementation. It is likely that your `products` variable is not set correctly on purchases, which is typically undesired behavior.
