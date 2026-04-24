---
title: dynamicAccountSelection
description: The dynamicAccountSelection variable enables or disables dynamic account selection.
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
role: Developer
TQID: https://experienceleague.adobe.com/tne4K1ppeYbWGckTmuJy0f8Bjdw9WvGbjrOSKs4RXlk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# dynamicAccountSelection

>[!IMPORTANT]
>
>Dynamic accounts are only supported using legacy JavaScript implementations (H Code). These variables are not supported in current AppMeasurement libraries or Adobe Experience Platform Data Collection.

The `dynamicAccountSelection` variable is a boolean that determines if dynamic account selection is used.

If set to `true`, the JavaScript file looks at `dynamicAccountMatch` and `dynamicAccountList`.

If set to `false`, or if this variable is not defined, the `dynamicAccountMatch` and `dynamicAccountList` variables are ignored.

If this variable is not defined, the default value is `false`.

## Syntax

```js
s.dynamicAccountSelection = [boolean];
```

## Example

```js
s.dynamicAccountSelection = true;
```
