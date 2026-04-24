---
title: linkTrackEvents
description: Determine what events to include in link tracking image requests.
feature: Appmeasurement Implementation
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
role: Admin, Developer
TQID: https://experienceleague.adobe.com/7BKaDxchTRu39doWzm8f32DOemgpvj1s-4uzfjJkOEA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
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
# linkTrackEvents

Some implementations don't want to include all variables in all link tracking image requests. Use the [`linkTrackVars`](linktrackvars.md) and `linkTrackEvents` variables to selectively include dimensions and metrics in [`tl()`](../functions/tl-method.md) calls.

This variable is not used for page view calls ([`t()`](../functions/t-method.md) method).

## Determine which Analytics events to include in an XDM event using the Web SDK

The Web SDK does not exclude certain fields for link tracking calls. However, you can use the `onBeforeEventSend` callback to clear or set desired fields before data is sent to Adobe. See [Modifying events globally](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) in the Web SDK documentation for more information.

## Events in link tracking calls using the Adobe Analytics extension

Adobe Experience Platform automatically includes defined events in link tracking hits if you do not use custom code.

>[!IMPORTANT]
>
>If you set events in Analytics extension's custom code editor, you must include the event in `linkTrackEvents` using custom code as well.

## s.linkTrackEvents in AppMeasurement and the Analytics extension custom code editor

The `s.linkTrackEvents` variable is a string containing a comma-delimited list of events that you want to include in link tracking image requests (`tl()` method). The following three criteria must be met to include metrics in link tracking hits:

* Set the desired event in the [`events`](../page-vars/events/events-overview.md) variable. For example, `s.events = "event1";`.
* Set the `events` variable in `linkTrackVars`. For example, `s.linkTrackVars = "events";`.
* Set the desired event in the `linkTrackEvents` variable. For example, `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

The default value for this variable is an empty string. If this variable is not defined, all events are included in link tracking image requests. Note that Data Collection automatically populates this variable based on events set in the interface, so it is always set for implementations that use tags in Adobe Experience Platform.

>[!TIP]
>
>Avoid using the Analytics object identifier (`s.`) when specifying events in this variable. For example, `s.linkTrackEvents = "event1";` is correct, while `s.linkTrackEvents = "s.event1";` is incorrect.

## Example

The following link tracking function includes only `event1` (not `event2`) in the image request sent to Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
