---
title: Unique visitors
description: The number of unique visitor IDs.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
---
# Unique visitors

The 'Unique visitors' [metric](overview.md) shows the number of visitor IDs for the dimension item. It is one of the most common metrics used when determining traffic, as it gives a high-level overview of the popularity of a dimension item. For example, a visitor can come to your site every day for a month, but they still count as a single unique visitor.

If you use [Cross-device analytics](../cda/overview.md), this metric is replaced with the [Unique devices](unique-devices.md) metric.

## Daily, weekly, monthly, quarterly, and yearly unique visitors

Analysis Workspace treats unique visitors based on the granularity of the report. For example, if you use the [Day](../dimensions/day.md) dimension, you'll see daily unique visitors for each dimension item. However, for the report total, it is deduplicated unique visitors for the freeform table's date range.

## How this metric is calculated

This metric counts the number of unique visitor IDs for a given dimension item. See [Visitor identification overview](/help/implement/id/overview.md) for more information on how Adobe Analytics identifies unique visitors.
