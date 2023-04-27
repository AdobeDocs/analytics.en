---
title: usePlugins
description: Enable or disable the doPlugins() function.
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
---
# usePlugins

If `usePlugins` is enabled, the [`doPlugins()`](../functions/doplugins.md) function runs just before AppMeasurement compiles and sends a hit to Adobe. Enable this variable if you use the `doPlugins()` function.

## Use the `onBeforeEventSend` callback using the Web SDK

While the Web SDK does not have a boolean to handle the execution of additional logic before data is sent to Adobe, you can register the `onBeforeEventSend` callback to modify data. See [Modifying events globally](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) in the Web SDK documentation for more information.

## Use Plug-ins using the Adobe Analytics extension

Adobe provides an extension labeled 'Common Analytics Plugins' that allows you to call most [Plug-ins](../plugins/impl-plugins.md). Install the extension, and call the desired plug-in within a rule.

If the desired plug-in is not included in the Adobe extension, use the custom code editor following AppMeasurement syntax.

## s.usePlugins in AppMeasurement and the Analytics extension custom code editor

The `s.usePlugins` variable is a boolean that determines if AppMeasurement calls the `doPlugins()` function. Its default value is `false`. Set this variable to `true` if you use the `doPlugins()` function in your implementation.

```js
s.usePlugins = true;
```
