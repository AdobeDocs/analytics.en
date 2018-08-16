---
description: Explains how to create a metric that shows which campaigns assist in conversion.
seo-description: Explains how to create a metric that shows which campaigns assist in conversion.
seo-title: Order Assists Metric
title: Order Assists Metric
uuid: a8f665fd-e122-401f-9b73-71acb29348a4
index: y
internal: n
snippet: y
translate: y
---

# Order Assists Metric


1. In the Calculated Metrics Builder, name the metric something like "Order Assists".
1. In the Definition canvas, drag in an Orders metric, but change the allocation to "Participation." Participation is similar to linear allocation, except full credit is given to all values. ![](assets/cm_orders_allocation.png) 

1. Drag in another Orders metric below this one, but leave the default (last touch) allocation.
1. Change the operator between the two metrics to a minus (-).This will subtract all orders where allocation went to the last campaign before the order. ![](assets/campaign_assists.png) 

1. Save the metric.
1. Apply it to the External Campaigns report: ![](assets/cm_ext_campaign.png) 

This is an easy way to tell which campaigns assisted in the conversion of orders. 
