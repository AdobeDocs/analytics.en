---
title: Color depth
description: The color depth of the device.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Color depth

The 'Color depth' [dimension](overview.md) reports how many colors that the device supports. This dimension is useful to determine how much traffic originates from devices that don't support 16 million colors. Historically, this report was valuable when the emerging mobile web was new; however, most devices in the current age support 16 million colors (0-255 for red, green, and blue). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Populate this dimension with data

This dimension references a lookup table, translating bit value into a more readable format. It collects data from the [`c` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement uses the `screen.colorDepth` variable to populate the image request query string. If you use AppMeasurement (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `c` query string parameter on each hit with a valid bit value.

## Dimension items

Dimension items include the number of colors supported by the device. Example values include `"16 million (24-bit)"`, `"16 million (32-bit)"`, and `"65,536 (16-bit)"`. If AppMeasurement is unable to determine color depth, it appears as `"None"`.

>[!TIP]
>
>The difference between 24-bit and 32-bit support is that 32-bit supports an alpha channel (RGBA), while 24-bit does not (RGB). See [Color depth](https://en.wikipedia.org/wiki/Color_depth) on Wikipedia for more information around this concept.
