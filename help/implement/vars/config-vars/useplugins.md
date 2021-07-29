---
title: usePlugins
description: Enable or disable the doPlugins() function.
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
---
# usePlugins

If `usePlugins` is enabled, the [`doPlugins()`](../functions/doplugins.md) function runs just before AppMeasurement compiles and sends a hit to Adobe. Enable this variable if you use the `doPlugins()` function.

## Use Plug-ins using tags in Adobe Experience Platform

There is not a dedicated field in the Data Collection UI to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.usePlugins in AppMeasurement and custom code editor

The `s.usePlugins` variable is a boolean that determines if AppMeasurement calls the `doPlugins()` function. Its default value is `false`. Set this variable to `true` if you use the `doPlugins()` function in your implementation.

```js
s.usePlugins = true;
```
