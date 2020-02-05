---
title: usePlugins
description: Enable or disable the doPlugins() function.
---

# usePlugins

If `usePlugins` is enabled, the `doPlugins()` function runs just before AppMeasurement compiles and sends a hit to Adobe. Enable this variable if you use the `doPlugins()` function.

## Use Plug-ins in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.usePlugins in AppMeasurement and Launch custom code editor

The `s.usePlugins` variable is a boolean that determines if AppMeasurement calls the `doPlugins()` function. Its default value is `false`. Set this variable to `true` if you use the `doPlugins()` function in your implementation.

```js
s.usePlugins = true;
```
