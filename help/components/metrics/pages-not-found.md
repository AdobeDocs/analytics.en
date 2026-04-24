---
title: Pages not found (metrics)
description: The number of hits containing an error.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
TQID: https://experienceleague.adobe.com/V5jVT8wh71qMrchQmmM6c4EMofHPUEI388TmAf7Zf6M
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
# Pages not found

*This help page describes how 'Pages not found' works as a metric. See the [Pages not found](../dimensions/pages-not-found.md) dimension page for more information on how it works as a dimension.*

The 'Pages not found' [metric](overview.md) shows the number of hits where a dimension was set or persisted at the time a visitor encountered an error. This metric is valuable when you want to see which pages or URLs contained error messages (such as a 404). You can then pass this information on to your web development team, who can determine the cause of the error and fix it.

## How this metric is calculated

This metric counts all hits where the [`pageType`](/help/implement/vars/page-vars/pagetype.md) variable equals the value of `"errorPage"`. It is the metric equivalent of the [Pages not found](../dimensions/pages-not-found.md) dimension.
