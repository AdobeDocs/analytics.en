---
title: Custom link
description: The name of the custom link.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
TQID: https://experienceleague.adobe.com/x4IAGJjozPnLsft1e9xs68L6TNDJbHW0H4Z23p9EDNg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Custom link

The 'Custom link' [dimension](overview.md) reports the names of custom links implemented on your site. Custom links are a flexible tracking mechanism for any interaction that is not a file download or outbound navigation. Common examples include button clicks, internal navigation, or form interactions. This dimension is valuable when you want to understand which of these interactions visitors engage with most.

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
