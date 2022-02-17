---
title: Product views
description: The number of views to product pages.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
---
# Product views

The 'Product views' metric shows the number of times any product was viewed. This metric is useful when you want to see your top-viewed products, or see how total product views trend over time.

## How this metric is calculated

This metric counts the number of hits that match **either** of the following:

* The value `prodView` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable; or
* The [`products`](/help/implement/vars/page-vars/products.md) variable is set, and no shopping cart events exist in the `events` variable. Any event that is not custom (`event1` - `event1000`) is a shopping cart event.
