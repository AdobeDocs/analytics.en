---
title: decodeLinkParameters
description: Enable or disable AppMeasurement double-encoding link tracking variables.
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Appmeasurement Implementation
role: Admin, Developer
TQID: https://experienceleague.adobe.com/YzBsuWvpzof1f8qqJO5j8wuWvHSWdPomxowisPbkg7E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# decodeLinkParameters

The `decodeLinkParameters` variable is a boolean that determines if link tracking variables get encoded once (if set to `true`) or twice (if set to `false`). It impacts only `linkName` (part of the [`tl()`](../functions/tl-method.md) method) and [`linkURL`](linkurl.md). It requires AppMeasurement v2.24.0 or higher to use. The default value of this variable is `false`.

In versions of AppMeasurement before v2.24.0, link tracking variables were always URL encoded twice. While not an issue for implementations that typically rely on single-byte characters, the double encoding created incorrectly encoded values for multi-byte characters in reports. Setting this variable to `true` encodes link tracking values once, which is typically the desired behavior.

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
