---
title: forceOffline
description: Manually set the online state of AppMeasurement.
feature: Variables
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
---
# forceOffline

The `forceOffline()` method lets you override the automatically detected state of AppMeasurement.

>[!IMPORTANT]
>
>Only use this function when [`trackOffline`](../config-vars/trackoffline.md) is enabled. Using this function outside of offline tracking can cause data loss.

AppMeasurement automatically detects the online state of the device. You can use the `forceOffline()` method to force AppMeasurement to treat hits as if the device was offline. This method does not take any arguments, and does not return any value. Its only purpose is to override the online state in AppMeasurement.

## Force Offline using tags in Adobe Experience Platform

There is not a dedicated field in the Data Collection UI to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.forceOffline() in AppMeasurement and custom code editor

You can call the `s.forceOffline()` method anywhere in your implementation after you instantiate the Analytics object.

```js
s.forceOffline();
```
