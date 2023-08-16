---
title: Pages not found (metrics)
description: The number of hits containing an error.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
---
# Pages not found

*This help page describes how 'Pages not found' works as a metric. See the [Pages not found](../dimensions/pages-not-found.md) dimension for more information.*

The 'Pages not found' metric shows the number of hits where a dimension was set or persisted at the time a visitor encountered an error. This metric is valuable when you want to see which pages or URLs contained error messages (such as a 404). You can then pass this information on to your web development team, who can determine the cause of the error and fix it.

## How this metric is calculated

This metric counts all hits where the [`pageType`](/help/implement/vars/page-vars/pagetype.md) variable equals the value of `"errorPage"`. It is the metric equivalent of the [Pages not found](../dimensions/pages-not-found.md) dimension.
