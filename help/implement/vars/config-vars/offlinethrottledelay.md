---
title: offlineThrottleDelay
description: Establishes the frequency of hits when a device comes back online.
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
---
# offlineThrottleDelay

Offline tracking is an optional way to collect data in Adobe Analytics. If a visitor disconnects from the internet but continues to browse your site, hits are stored in an offline queue until the device reconnects to the internet. Offline tracking is mostly used for mobile applications.

When a device comes back online, all hits stored on the device are sent to Adobe data collection servers. Large numbers of queued hits can potentially impact performance on older devices. Use the `offlineThrottleDelay` variable to establish how often queued hits are sent to Adobe.

## Offline Throttle Delay using tags in Adobe Experience Platform

There is not a dedicated field in the Data Collection UI to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.offlineThrottleDelay in AppMeasurement and custom code editor

The `s.offlineThrottleDelay` variable is an integer that represents the number of milliseconds AppMeasurement waits between sending queued hits. Its default value is `0`, meaning all queued hits are sent at once. If `trackOffline` is `false`, this variable does nothing.

```js
s.offlineThrottleDelay = 500;
```
