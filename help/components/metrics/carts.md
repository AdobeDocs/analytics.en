---
title: Carts
description: The number of hits where a visitor added their first product to a cart.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
TQID: https://experienceleague.adobe.com/a-qT5Ly8-4mSBGbGTAzbwLIMRFZtqotMPvGFgOrM41Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
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
---
# Carts

The 'Carts' [metric](overview.md) shows the number of hits where a visitor added their first product to a cart.

## How this metric is calculated

This metric counts the number of hits where `scOpen` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.

## Difference between 'Carts', 'Cart views', and 'Cart additions'

Since 'Carts', 'Cart views', and 'Cart additions' are events that require implementation, your organization decides the precise difference between these metrics. However, Adobe designed these metrics for the following logic:

* 'Carts' only triggers once per purchase when a visitor adds their first product to their shopping cart.
* 'Cart views' triggers every time a visitor views their shopping cart.
* 'Cart additions' triggers for every product added to their cart.

When a customer adds their first product to a shopping cart, the intended behavior is that both 'Carts' and 'Cart additions' trigger. Again, these guidelines are not concrete; your organization determines the exact implementation logic.
