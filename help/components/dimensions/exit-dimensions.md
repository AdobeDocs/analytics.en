---
title: Exit dimensions
description: Lists exit dimensions and their use.
keywords: exit page, exit site section, exit server, exit custom insight
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
TQID: https://experienceleague.adobe.com/YRjvhW8OzBlip9ok0-1D4rYSljkccpIAlDkqCQv7nyo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
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
# Exit dimensions

*This help page describes how exits work as a [dimension](overview.md). For information on how exits work as a metric, see the [Exits](../metrics/exits.md) metric.*

Exit dimensions record the last dimension item, and retroactively apply it to all hits in the visit. Exit dimensions are available for all variables with pathing enabled under [Traffic variables](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) in Report suite settings.

## Populate exit dimensions with data

A given exit dimension is based on its associated traffic variable. If the non-exit variable has data, its associated exit dimension also contains data. No implementation changes are required for exit dimensions if your traffic variables contain data.

## Dimension items

Since exit variables are typically based on custom strings in your implementation, your organization determines what the dimension items are. Values in a given exit dimension match dimension items in its associated non-exit dimension. For example, dimension items in the 'Exit page' dimension contain similar dimension items in the 'Page' dimension.
