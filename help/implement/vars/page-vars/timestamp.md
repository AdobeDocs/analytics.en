---
title: timestamp
description: Manually set the timestamp of the hit.
feature: Variables
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
---
# timestamp

The `timestamp` variable manually sets the timestamp of the hit for timestamp-enabled report suites.

>[!WARNING]
>
>Do not use this variable if your report suite is not explicitly configured to accept timestamped hits. AppMeasurement automatically sets the time of a hit for report suites that do not support timestamped hits. If you send a hit with this variable to a report suite that does not support timestamps, that data is permanently lost.

## Timestamp using the Web SDK

Timestamp is [mapped for Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under the XDM field `_experience.analytics.session.timestamp`. This field only supports Unix time.

## Timestamp using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.timestamp in AppMeasurement and the Analytics extension custom code editor

The `s.timestamp` variable is a string containing the date and time of the hit. Valid timestamp formats include [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) and [Unix time](https://en.wikipedia.org/wiki/Unix_time).

```js
// Timestamp using ISO 8601
s.timestamp = "2020-01-01T00:00:00Z";

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
* The date can be in standard or extended format. For example, `2020-01-01T00:00:00Z` and `20200101T000000Z` are both valid.
* Fractional minutes and seconds are technically valid, but the fractions are ignored by Adobe.
* Time zones are supported in standard and extended formats.

The following are valid example ISO 8601 values in the `timestamp` variable:

```text
2020-01-01T00:00:00+00:00
2020-01-01T00:00:00Z
2020-01-01T00:00:00
2020-01-01T00:00
20200101T000000+0000
20200101T000000Z
20200101T000000
20200101T0000
```
