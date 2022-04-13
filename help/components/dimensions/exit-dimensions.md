---
title: Exit dimensions
description: Lists exit dimensions and their use.
keywords: exit page, exit site section, exit server, exit custom insight
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
---
# Exit dimensions

*This help page describes how exits work as a dimension. For information on how exits work as a metric, see the [Exits](../metrics/exits.md) metric.*

Exit dimensions record the last dimension item, and retroactively apply it to all hits in the visit. Exit dimensions are available for all variables with pathing enabled under [Traffic variables](/help/admin/admin/c-traffic-variables/traffic-var.md) in Report suite settings.

## Populate exit dimensions with data

A given exit dimension is based on its associated traffic variable. If the non-exit variable has data, its associated exit dimension also contains data. No implementation changes are required for exit dimensions if your traffic variables contain data.

## Dimension items

Since exit variables are typically based on custom strings in your implementation, your organization determines what the dimension items are. Values in a given exit dimension match dimension items in its associated non-exit dimension. For example, dimension items in the 'Exit page' dimension contain similar dimension items in the 'Page' dimension.
