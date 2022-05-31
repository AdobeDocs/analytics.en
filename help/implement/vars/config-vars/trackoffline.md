---
title: trackOffline
description: Enable or disable offline tracking, which changes how AppMeasurement collects data.
feature: Variables
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
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

## Track Offline using tags in Adobe Experience Platform

There is not a dedicated field in the Data Collection UI to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.trackOffline in AppMeasurement and custom code editor

The `s.trackOffline` variable is a boolean that enables or disables offline tracking. Its default value is `false`. Set this value to `true` if you want to enable offline tracking.

```js
s.trackOffline = true;
```
