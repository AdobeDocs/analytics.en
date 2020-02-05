---
title: linkTrackEvents
description: Determine what events to include in link tracking image requests.
---

# linkTrackEvents

Some implementations don't want to include all variables in all link tracking image requests. Use the `linkTrackVars` and `linkTrackEvents` variables to selectively include dimensions and metrics in `tl()` calls.

This variable is not used for page view calls (`t()` function).

## Events in link tracking calls using Adobe Experience Platform Launch

Launch automatically detects events defined in the interface and includes them in link tracking hits.

> [!IMPORTANT] If you set events in Launch using the custom code editor, you must include the event in `linkTrackEvents` using custom code as well.

## s.linkTrackEvents in AppMeasurement and Launch custom code editor

The `s.linkTrackEvents` variable is a string containing a comma-delimited list of events that you want to include in link tracking image requests (`tl()` function). The following three criteria must be met to include metrics in link tracking hits:

* Set the desired event in the `events` variable. For example, `s.events = "event1";`.
* Set the `events` variable in `linkTrackVars`. For example, `s.linkTrackVars = "events";`.
* Set the desired event in the `linkTrackEvents` variable. For example, `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

The default value for this variable is an empty string. If this variable is not defined, all events are included in link tracking image requests. Note that Launch automatically populates this variable based on events set in the interface, so it is always set in implementations using Launch.

> [!TIP] Avoid using the Analytics object identifier (`s.`) when specifying events in this variable. For example, `s.linkTrackEvents = "event1";` is correct, while `s.linkTrackEvents = "s.event1";` is incorrect.

## Example

The following link tracking function includes only `event1` (not `event2`) in the image request sent to Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
