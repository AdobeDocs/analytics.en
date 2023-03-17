---
title: Visit number
description: The nth visit of the visitor.
feature: Dimensions
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
---
# Visit number

The 'Visit number' dimension reports which visit the visitor is currently on. When a new visit starts, this dimension item increases by 1. This dimension is helpful when you want to understand how engaged visitors are when returning to your site. It is a visit-based dimension, meaning that it contains the same value for the entire visit and cannot change. It applies to the lifetime of the visitor, regardless of project date range.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include the string `"Visit number"` followed by the numeric representation of the visit the visitor is currently on. For example, if the visitor has never been to your site before, their first visit belongs to the dimension item `"Visit number 1"`. If this is the visitor's 13th visit to your site, they belong to the dimension item `"Visit number 13"`.
