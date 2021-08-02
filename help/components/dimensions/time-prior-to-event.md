---
title: Time prior to event
description: The amount of time between the metric and the first hit of the visit.
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
---
# Time prior to event

The 'Time prior to event' dimension reports the amount of time that passed between the first hit of the visit and the desired metric. This dimension is useful to determine the amount of time it takes to hit a success event, such as a form submission or a purchase.

## Populate this dimension with data

While this dimension technically works out of the box for all implementations, it works best with custom and purchase events. Adobe recommends implementing custom events on your site. If you implement custom events, no additional implementation is required for this dimension.

## Dimension items

Dimension items include time-based buckets ranging from `"Less than 1 minute"` to `"More than 15 hours"`. For example, if it took a visitor 23 minutes from their first hit to a purchase, it would belong under the `"10 to 30 minutes"` dimension item. The buckets cannot be customized for this metric.
