---
title: offlineThrottleDelay
description: Establishes the frequency of hits when a device comes back online.
feature: Appmeasurement Implementation
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/FiC4yXkRmNoY0PPO9ouC8-hX5xqWhkbcDVht5f05Yqk'
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
# offlineThrottleDelay

Offline tracking is an optional way to collect data in Adobe Analytics. If a visitor disconnects from the internet but continues to browse your site, hits are stored in an offline queue until the device reconnects to the internet. Offline tracking is mostly used for mobile applications.

When a device comes back online, all hits stored on the device are sent to Adobe data collection servers. Large numbers of queued hits can potentially impact performance on older devices. Use the `offlineThrottleDelay` variable to establish how often queued hits are sent to Adobe.

## Offline throttle delay using the Web SDK

The Web SDK does not support offline tracking.

## Offline throttle delay using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.offlineThrottleDelay in AppMeasurement and the Analytics extension custom code editor

The `s.offlineThrottleDelay` variable is an integer that represents the number of milliseconds AppMeasurement waits between sending queued hits. Its default value is `0`, meaning all queued hits are sent at once. If `trackOffline` is `false`, this variable does nothing.

```js
s.offlineThrottleDelay = 500;
```
