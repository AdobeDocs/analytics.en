---
title: Identified state
description: A flag determining recognition by the device graph.
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
---
# Identified state

The 'Identified state' dimension is specific to [Cross-Device Analytics](../cda/overview.md) virtual report suites. It reports if the Experience Cloud ID is recognized by the device graph at the time the report is run. This dimension is helpful in understanding how well CDA stitches or "compresses" data.

## Populate this dimension with data

As long as you have [Cross-Device Analytics](../cda/overview.md) configured for a virtual report suite, this dimension works out of the box.

## Dimension items

Dimension items include `"Identified"` and `"Unidentified"`.

* **`"Identified"`**: The device graph recognizes the Experience Cloud ID tied to the hit.
* **`"Unidentified"`**: The device graph does not recognize the Experience Cloud ID, or the hit does not have an Experience Cloud ID.
