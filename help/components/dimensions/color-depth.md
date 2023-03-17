---
title: Color depth
description: The color depth of the device.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
---
# Color depth

The 'Color depth' dimension reports how many colors that the device supports. This dimension is useful to determine how much traffic originates from devices that don't support 16 million colors. Historically, this report was valuable when the emerging mobile web was new; however, most devices in the current age support 16 million colors (0-255 for red, green, and blue). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Populate this dimension with data

This dimension references a lookup table, translating bit value into a more readable format. It collects data from the [`c` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement uses the `screen.colorDepth` variable to populate the image request query string. If you use AppMeasurement (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `c` query string parameter on each hit with a valid bit value.

## Dimension items

Dimension items include the number of colors supported by the device. Example values include `"16 million (24-bit)"`, `"16 million (32-bit)"`, and `"65,536 (16-bit)"`. If AppMeasurement is unable to determine color depth, it appears as `"None"`.

>[!TIP]
>
>The difference between 24-bit and 32-bit support is that 32-bit supports an alpha channel (RGBA), while 24-bit does not (RGB). See [Color depth](https://en.wikipedia.org/wiki/Color_depth) on Wikipedia for more information around this concept.
