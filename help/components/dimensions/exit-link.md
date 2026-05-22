---
title: Exit link
description: The name of the exit link.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
TQID: https://experienceleague.adobe.com/lGKBkR5e2arJxGmfIE4qN84oGtYJ2zkfn6luqxEUJ-w
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
# Exit link

The 'Exit link' [dimension](overview.md) reports the names of exit links implemented on your site. Exit links track outbound clicks that navigate visitors away from the current domain. This dimension is valuable when you want to understand which outbound links are clicked most frequently.

## Populate this dimension with data

This dimension collects data from the [`pev2` query string](/help/implement/validate/query-parameters.md) in image requests, depending on the value in the `pe` query string. The `pe` query string determines which link dimension receives the `pev2` value:

* **[Custom link](custom-link.md)**: `lnk_o`
* **[Download link](download-link.md)**: `lnk_d`
* **Exit link** (this page): `lnk_e`

If `pev2` is not provided, the link URL (`pev1`) is used as the dimension value instead. When a link name is explicitly provided, the maximum length is 100 bytes. Values derived from the link URL are not subject to this limit.

To populate this dimension using AppMeasurement, send a [`tl()`](/help/implement/vars/functions/tl-method.md) image request with a link type argument of `"e"`. Set the link name argument to the desired value:

```js
s.tl(true,"e","Example exit link");
```

## Dimension items

Since this variable is based on a custom string in your implementation, your organization determines what the dimension items are. Adobe recommends that you group links into meaningful categories based on your reporting needs. If no link name is provided, dimension items appear as raw URLs instead. These raw URLs are harder to interpret in reports, so provide a descriptive link name wherever possible.
