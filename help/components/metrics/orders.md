---
title: Orders
description: The number of purchases made.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
---
# Orders

The 'Orders' metric shows the total number of purchase events made on your site. This metric is vital for eCommerce sites in measuring conversion. You can combine this metric with any dimension to see what which dimension items contributed to an order. For example, you could see the top campaigns (using the [Tracking code](../dimensions/tracking-code.md) dimension) or top internal search terms (using an [eVar](../dimensions/evar.md)) that contributed to purchases.

## How this metric is calculated

This metric counts the number of hits where `purchase` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.
