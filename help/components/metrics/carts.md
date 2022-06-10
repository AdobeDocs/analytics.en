---
title: Carts
description: The number of hits where a visitor added their first product to a cart.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
---
# Carts

The 'Carts' metric shows the number of hits where a visitor added their first product to a cart.

## How this metric is calculated

This metric counts the number of hits where `scOpen` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.

## Difference between 'Carts', 'Cart views', and 'Cart additions'

Since 'Carts', 'Cart views', and 'Cart additions' are events that require implementation, your organization decides the precise difference between these metrics. However, Adobe designed these metrics for the following logic:

* 'Carts' only triggers once per purchase when a visitor adds their first product to their shopping cart.
* 'Cart views' triggers every time a visitor views their shopping cart.
* 'Cart additions' triggers for every product added to their cart.

When a customer adds their first product to a shopping cart, the intended behavior is that both 'Carts' and 'Cart additions' trigger. Again, these guidelines are not concrete; your organization determines the exact implementation logic.
