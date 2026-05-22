---
title: forceOnline
description: Manually set the online state of AppMeasurement.
feature: Appmeasurement Implementation
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/qPSlGDmNTccOtGRvlu-xr-wf1hV18OA-yyiuScnZr7g'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
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
