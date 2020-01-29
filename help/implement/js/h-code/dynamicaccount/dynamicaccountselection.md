---
title: dynamicAccountSelection
description: The dynamicAccountSelection variable enables or disables dynamic account selection.
---

# dynamicAccountSelection

> [!IMPORTANT] Dynamic accounts are only supported using legacy JavaScript implementations (H Code). These variables are not supported in current AppMeasurement libraries or Adobe Experience Platform Launch.

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
