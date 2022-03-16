---
title: Single page visits (dimensions)
description: A flag indicating that the visit consisted of a single page.
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
---
# Single page visits

*This help page describes how 'Single page visits' works as a dimension. See the [Single page visits](../metrics/single-page-visits.md) metric for more information.*

The 'Single page visits' dimension reports the number of visits that consisted of a single unique [Page](page.md) dimension item. It is the dimension form of the [Single page visits](../metrics/single-page-visits.md) metric.

This dimension is most commonly used as a component within [segmentation](../segmentation/seg-home.md). It is not typically used as a dimension in reports.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

The only dimension item is `"Enabled"`. If a visit consists of a single page, the hit is set to this value. All other hits are omitted from this report.
