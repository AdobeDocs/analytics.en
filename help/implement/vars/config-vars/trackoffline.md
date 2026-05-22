---
title: trackOffline
description: Enable or disable offline tracking, which changes how AppMeasurement collects data.
feature: Appmeasurement Implementation
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/6VDAO0-QMXqia2Ddy1uPcxnTrlJi49B8zjaLcC0HawU'
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# trackOffline

Offline tracking is an optional way to collect data in Adobe Analytics. If a visitor disconnects from the internet but continues to browse your site, hits are stored in an offline queue until the device reconnects to the internet. Offline tracking is mostly used for mobile applications.

The `trackOffline` variable determines if you want to use offline tracking in your implementation.

>[!WARNING]
>
>You must configure your report suite to accept timestamped hits before enabling this variable. If a report suite does not accept timestamped hits and this variable is enabled, that data is lost and cannot be recovered.

When enabled, AppMeasurement uses the following process to send data to Adobe:

* When compiling an image request, a timestamp query string parameter is included.
* If the device cannot reach Adobe data collection servers, the hit is stored locally on the device.
* During each subsequent hit, AppMeasurement attempts to send an image request to Adobe.
  * If it cannot reach Adobe data collection servers, the hit is added to the queue on the device.
  * If it can reach Adobe data collection servers, the hit and the queue of hits while the device was offline are sent.

## Offline tracking using the Web SDK

The Web SDK does not support offline tracking.

## Offline tracking using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.trackOffline in AppMeasurement and the Analytics extension custom code editor

The `s.trackOffline` variable is a boolean that enables or disables offline tracking. Its default value is `false`. Set this value to `true` if you want to enable offline tracking.

```js
s.trackOffline = true;
```
