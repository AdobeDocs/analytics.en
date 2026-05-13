---
title: Identified state
description: A flag determining recognition for stitching.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
TQID: https://experienceleague.adobe.com/JUBtgXBDboIgX0xbvuflF5q-oEwqHx4vKvJd0Y5XMLY
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
---
# Identified state

The 'Identified state' [dimension](overview.md) is specific to [Cross-Device Analytics](../cda/overview.md) virtual report suites. It reports if hits are identified (stitched) or not by the system at the time the report is run. This dimension is helpful in understanding how well CDA stitches or "compresses" data.

## Populate this dimension with data

As long as you have [Cross-Device Analytics](../cda/overview.md) configured for a virtual report suite, this dimension works out of the box.

## Dimension items

Dimension items include `"Identified"` and `"Unidentified"`.

* **`"Identified"`**: The hit is mapped to a person.
* **`"Unidentified"`**: The hit is not mapped to a person and could not be mapped by any attribution method.
