---
title: usePlugins
description: Enable or disable the doPlugins() function.
feature: Appmeasurement Implementation
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/7ofbF5EloAUlvCmGv-CaTFxxZELX0wydJ8HzmU2f6EQ'
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
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
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
