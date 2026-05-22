---
title: timestamp
description: Manually set the timestamp of the hit.
feature: Appmeasurement Implementation
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/f2r9jWtF5HgCP6jUKg3YnLFxNwx1DiUBI-2Nquy5-K0'
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
# timestamp

The `timestamp` variable manually sets the timestamp of the hit for timestamp-enabled report suites.

>[!WARNING]
>
>Do not use this variable if your report suite is not explicitly configured to accept timestamped hits. AppMeasurement automatically sets the time of a hit for report suites that do not support timestamped hits. If you send a hit with this variable to a report suite that does not support timestamps, that data is permanently lost.

## Timestamp using the Web SDK

Timestamp is [mapped for Adobe Analytics](/help/implement/aep-edge/xdm-var-mapping.md) under the XDM field `xdm.timestamp`. This field only supports Unix time.

## Timestamp using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.timestamp in AppMeasurement and the Analytics extension custom code editor

The `s.timestamp` variable is a string containing the date and time of the hit. Valid timestamp formats include [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) and [Unix time](https://en.wikipedia.org/wiki/Unix_time) in seconds.

```js
// Timestamp using ISO 8601
s.timestamp = "2024-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## ISO 8601 values

Dates and times expressed in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) can take several different forms. Adobe does not support all features in ISO 8601.

* Both the date and time must be provided, separated by `T`.
* Hours and minutes are required; seconds are optional but recommended.
* Week dates and ordinal dates are not supported.
* The date can be in standard or extended format. For example, `2024-01-01T00:00:00Z` and `20240101T000000Z` are both valid.
* Fractional minutes and seconds are technically valid, but the fractions are ignored by Adobe.
* Time zones are supported in standard and extended formats.

The following are valid example ISO 8601 values in the `timestamp` variable:

```text
2024-01-01T00:00:00+00:00
2024-01-01T00:00:00Z
2024-01-01T00:00:00
2024-01-01T00:00
20240101T000000+0000
20240101T000000Z
20240101T000000
20240101T0000
```
