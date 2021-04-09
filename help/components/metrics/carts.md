---
title: Carts
description: The number of hits where a visitor added their first product to a cart.
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
---
# Carts

The 'Cart removals' metric shows the number of times a visitor removed something from their cart. This metric is helpful when you want to understand the part of the conversion funnel where customers are no longer interested in a product.

## How this metric is calculated

This metric counts the number of hits where `scOpen` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.

## Difference between 'Carts' and 'Cart views'

Since 'Carts' and 'Cart views' are events that require implementation, your organization decides the precise difference between these two metrics. However, Adobe designed these metrics for the following:

* 'Carts' only triggers once per purchase when a visitor adds their first product to their shopping cart.
* 'Cart additions' triggers for every product added to their cart.

For the first product, both 'Carts' and 'Cart additions' trigger. Again, these guidelines are not concrete; your organization determines the exact implementation logic.
