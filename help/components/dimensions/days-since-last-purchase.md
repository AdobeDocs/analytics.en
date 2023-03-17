---
title: Days since last purchase
description: The number of days between the current hit and the last purchase that they made.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
---
# Days since last purchase

The 'Days since last purchase' dimension measures the amount of time passed between the current hit of the visitor and their most recent purchase at that time. This dimension helps you understand behavior visitors make after purchasing something on your site.

Visitors that have never purchased something are not included in this dimension. Additionally, hits fired before a visitor's first purchase are not included either. Only hits after the visitor's first purchase are included.

## Populate this dimension with data

Adobe automatically populates this dimension based on the [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) event in your implementation. If you implement the `purchase` event on your site, this dimension always works.

## Dimension items

Dimension items include the number of days between a visitor's most recent purchase and the current hit. Each number of days is a separate dimension item, with "Same day" occurring where a visitor's most recent purchase and the current hit happened on the same day.
