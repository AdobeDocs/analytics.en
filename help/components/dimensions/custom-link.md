---
title: Custom link
description: The name of the custom link.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
---
# Custom link

The 'Custom link' [dimension](overview.md) reports the names of custom links implemented on your site. Custom links are a flexible tracking mechanism for any interaction that is not a file download or outbound navigation. Common examples include button clicks, internal navigation, form interactions, and video events. This dimension is valuable when you want to understand which of these interactions visitors engage with most.

## Populate this dimension with data

This dimension collects data from the [`pev2` query string](/help/implement/validate/query-parameters.md) in image requests, depending on the value in the `pe` query string. The `pe` query string determines which link dimension receives the `pev2` value:

* **Custom link** (this page): `lnk_o`
* **[Download link](download-link.md)**: `lnk_d`
* **[Exit link](exit-link.md)**: `lnk_e`

If `pev2` is not provided, the link URL (`pev1`) is used as the dimension value instead. When a link name is explicitly provided, the maximum length is 100 bytes. Values derived from the link URL are not subject to this limit.

To populate this dimension using AppMeasurement, send a [`tl()`](/help/implement/vars/functions/tl-method.md) image request with a link type argument of `"o"`. Set the link name argument to the desired value:

```js
s.tl(true,"o","Example custom link");
```

## Dimension items

Since this variable is based on a custom string in your implementation, your organization determines what the dimension items are. Adobe recommends that you group links into meaningful categories based on your reporting needs. If no link name is provided, dimension items appear as raw URLs instead. These raw URLs are harder to interpret in reports, so provide a descriptive link name wherever possible.
