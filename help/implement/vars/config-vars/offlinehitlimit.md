---
title: offlineHitLimit
description: Determine the maximum number of hits to queue for offline tracking.
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
---
# offlineHitLimit

Offline tracking is an optional way to collect data in Adobe Analytics. If a visitor disconnects from the internet but continues to browse your site, hits are stored in an offline queue until the device reconnects to the Internet. Offline tracking is mostly used for mobile applications.

The `offlineHitLimit` variable places a cap on the number of hits the device stores locally. This variable only works if [`trackOffline`](trackoffline.md) is enabled.

## Offline hit limit using the Web SDK

The Web SDK does not support offline tracking.

## Offline hit limit using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.offlineHitLimit in AppMeasurement and the Analytics extension custom code editor

The `s.offlineHitLimit` variable is an integer representing the maximum number of hits that a device stores while they are offline. If this variable is not defined, it defaults to `10`. You can set it to any integer value. When setting high values, be mindful of local storage caps in a visitor's browser. This limit is typically 5 - 10 MB.

```js
s.offlineHitLimit = 100;
```
