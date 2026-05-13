---
title: Unique visitors
description: The number of unique visitor IDs.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
TQID: https://experienceleague.adobe.com/A0NvwoGPFLuS4e857eH-nMgmzAmz0EuGVQVDNBgiN4A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
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
# Unique visitors

The 'Unique visitors' [metric](overview.md) shows the number of visitor IDs for the dimension item. It is one of the most common metrics used when determining traffic, as it gives a high-level overview of the popularity of a dimension item. For example, a visitor can come to your site every day for a month, but they still count as a single unique visitor.

If you use [Cross-device analytics](../cda/overview.md), this metric is replaced with the [Unique devices](unique-devices.md) metric.

## Daily, weekly, monthly, quarterly, and yearly unique visitors

Analysis Workspace treats unique visitors based on the granularity of the report. For example, if you use the [Day](../dimensions/day.md) dimension, you'll see daily unique visitors for each dimension item. However, for the report total, it is deduplicated unique visitors for the freeform table's date range.

## How this metric is calculated

This metric counts the number of unique visitor IDs for a given dimension item. See [Visitor identification overview](/help/implement/id/overview.md) for more information on how Adobe Analytics identifies unique visitors.
