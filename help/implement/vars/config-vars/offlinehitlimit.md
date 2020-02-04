---
title: offlineHitLimit
description: Determine the maximum number of hits to queue for offline tracking.
---

# offlineHitLimit

Offline tracking is an optional way to collect data in Adobe Analytics. If a visitor disconnects from the internet but continues to browse your site, hits are stored in an offline queue until the device reconnects to the internet. Offline tracking is mostly used for mobile applications.

The `offlineHitLimit` variable places a cap on the number of hits the device stores locally. This variable only works if `trackOffline` is `true`.

## Offline Hit Limit in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.offlineHitLimit in AppMeasurement and Launch custom code editor

The `s.offlineHitLimit` variable is an integer representing the maximum number of hits a device stores while they are offline. If this variable is not defined, there is no limit to the number of hits a device stores while offline.

```js
s.offlineHitLimit = 100;
```
