---
title: forceOffline
description: Manually set the online state of AppMeasurement.
---

# forceOffline

The `forceOffline` method lets you override the automatically detected state of AppMeasurement.

> [!IMPORTANT] Only use this function when `trackOffline` is enabled. Using this function outside of offline tracking can cause data loss.

AppMeasurement automatically detects the online state of the device. You can use the `forceOffline` method to force AppMeasurement to treat hits as if the device was offline. This method does not take any arguments, and does not return any value. Its only purpose is to override the online state in AppMeasurement.

## Force Offline in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.forceOffline() in AppMeasurement and Launch custom code editor

You can call the `s.forceOffline()` method anywhere in your implementation after you instantiate the Analytics object.

```js
s.forceOffline();
```
