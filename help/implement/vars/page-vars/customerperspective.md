---
title: customerPerspective
description: Specifies whether a mobile app hit occurred while the app was in the foreground or background.
feature: Appmeasurement Implementation
role: Admin, Developer
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
---
# customerPerspective

The `customerPerspective` variable specifies whether a mobile app hit occurred while the app was in the foreground or the background. It is sent to Adobe data collection as the `cp` query parameter and populates the [Hit type](/help/components/dimensions/hit-type.md) dimension.

## Valid values

`customerPerspective` accepts the following string values:

* `foreground`: The hit occurred while the app was in active use.
* `background`: The hit occurred while the app was running in the background, such as a location update or a hit triggered by a push notification.

## How this variable is set

The Adobe Mobile SDK (version 4.13.6 and higher) sets `customerPerspective` automatically; you do not typically set it manually. Hits sent from a browser through AppMeasurement always report as `foreground`. If the variable is absent from a hit, that hit is treated as a foreground hit.

## Impact on reporting

The foreground/background distinction affects how visits are processed:

* Visits are counted only when they contain at least one foreground hit.
* Background hits can still be attributed to conversion events and can be analyzed through [context-aware sessions](/help/components/vrs/vrs-mobile-visit-processing.md) in virtual report suites. This behavior is useful when measuring the effectiveness of push notifications.
