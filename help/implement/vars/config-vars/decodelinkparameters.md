---
title: decodeLinkParameters
description: Enable or disable AppMeasurement double encoding link tracking variables.
exl-id: 7a4cea23-5ae6-4a8b-82a6-c68f9a1f9c49
feature: Variables
---
# decodeLinkParameters

The `decodeLinkParameters` variable is a boolean that determines if link tracking variables get encoded once (if set to `true`) or twice (if set to `false`). It impacts only `linkName` (part of the [`tl()`](../functions/tl-method.md) method) and [`linkURL`](linkurl.md). It requires AppMeasurement 2.24.0 or higher to use. The default value of this variable is `false`.

In previous versions of AppMeasurement, link tracking variables were always URL encoded twice. While not an issue for implementations that typically rely on single-byte characters, the double encoding created incorrectly encoded values for multi-byte characters in reports. Setting this variable to `true` encodes link tracking values once, which is typically the desired behavior.

* If your implementation uses multi-byte characters and link tracking variables are URL decoded to offset AppMeasurement's double encoding, set this variable to `false`. This value preserves existing AppMeasurement functionality.
* If your implementation uses multi-byte characters and you do not URL decode link tracking values, Adobe recommends setting this variable to `true`.
* If your implementation does not use multi-byte characters, this variable is not required. However, Adobe recommends setting this variable to `true` in cases where multi-byte characters might be sent.

## Double encode link parameters using the Web SDK

This variable is specific to AppMeasurement, and is not needed in any type of Web SDK implementation.

## Double encode link parameters using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.decodeLinkParameters in AppMeasurement and the Analytics extension custom code editor

The `s.decodeLinkParameters` variable is a boolean that determines if link tracking values get double encoded. If this variable is not defined, its default value is `false` to preserve functionality for existing implementations. Adobe recommends setting this value to `true` for all new implementations, especially if you see URL encoded values in link tracking reports.

```js
s.decodeLinkParameters = true;
```
