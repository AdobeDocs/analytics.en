---
title: forceOnline
description: Manually set the online state of AppMeasurement.
feature: Variables
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
---
# forceOnline

The `forceOnline()` method lets you override the automatically detected state of AppMeasurement.

>[!WARNING]
>
>Only use this method when [`trackOffline`](../config-vars/trackoffline.md) is enabled. Using this function outside of offline tracking can cause data loss.

AppMeasurement automatically detects the online state of the device. You can use the `forceOnline()` method to force AppMeasurement to treat hits as if the device was online. This method does not take any arguments, and does not return any value. Its only purpose is to override the online state in AppMeasurement.

## Force online using the Web SDK

The Web SDK does not support offline tracking.

## Force online using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.forceOnline() in AppMeasurement and the Analytics extension custom code editor

You can call the `s.forceOnline()` method anywhere in your implementation after you instantiate the Analytics object.

```js
s.forceOnline();
```
