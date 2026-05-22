---
title: Download link
description: The name of the download link.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
TQID: https://experienceleague.adobe.com/vok8Znalf6GBA1N0Z9GE1d31QpaUmD-d0bOsHB2Wehc
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
# Download link

The 'Download link' [dimension](overview.md) reports the names of download links implemented on your site. This dimension is valuable when you want to learn more about visitor behavior around download links, such as:

* Which files are downloaded most frequently from your site.
* Whether certain files are downloaded more often during specific time periods.
* Whether visitors download different file types when offered.

## Populate this dimension with data

This dimension collects data from the [`pev2` query string](/help/implement/validate/query-parameters.md) in image requests, depending on the value in the `pe` query string. The `pe` query string determines which link dimension receives the `pev2` value:

* **[Custom link](custom-link.md)**: `lnk_o`
* **Download link** (this page): `lnk_d`
* **[Exit link](exit-link.md)**: `lnk_e`

If `pev2` is not provided, the link URL (`pev1`) is used as the dimension value instead. When a link name is explicitly provided, the maximum length is 100 bytes. Values derived from the link URL are not subject to this limit.

To populate this dimension using AppMeasurement, send a [`tl()`](/help/implement/vars/functions/tl-method.md) image request with a link type argument of `"d"`. Set the link name argument to the desired value:

```js
s.tl(true,"d","Example download link");
```

## Dimension items

Since this variable is based on a custom string in your implementation, your organization determines what the dimension items are. Adobe recommends that you group links into meaningful categories based on your reporting needs. If no link name is provided, dimension items appear as raw URLs instead. These raw URLs are harder to interpret in reports, so provide a descriptive link name wherever possible.
