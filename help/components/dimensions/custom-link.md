---
title: Custom link
description: The name of the custom link.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
---
# Custom link

The 'Custom link' dimension reports the names of custom links implemented on your site. This dimension is valuable when you want to understand the types of links visitors click the most.

## Populate this dimension with data

This dimension collects data from the [`pev2` query string](/help/implement/validate/query-parameters.md) in image requests for hits that also have the `pe` query string with the value of `lnk_o`. If the `pe` query string has a different value in the hit, this dimension does not collect data.

If you want to send data to this dimension using AppMeasurement, send a [`tl()`](/help/implement/vars/functions/tl-method.md) image request with a link type argument of `"o"`. Populate the link name argument with the desired value.

## Dimension items

Since this variable is based on a custom string in your implementation, your organization determines what the dimension items are. Adobe recommends that you group links into meaningful categories based on your reporting needs.
