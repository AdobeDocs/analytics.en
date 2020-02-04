---
title: Event serialization
description: Help deduplicate metrics on your site.
---

# Event ID serialization

Event serialization is the process of implementing measures to prevent duplicate events from entering Analytics reporting. De-duplicating events is important in cases where you don't want metrics inflated by visitors refreshing the page.

> [!NOTE] Data Sources does not support event serialization or de-duplication.

## Set up event serialization

You must first set an event's [!UICONTROL Unique Event Recording] to [!UICONTROL Use Event ID] in report suite settings. See [Success Events](../../../../admin/admin/c-success-events/success-event.md) in the Admin user guide.

When using event IDs, de-duplication happens on the following levels:

* Each variable uses their own table for de-duplication. For example, `event1:ABC` and `event2:ABC` are both counted in reporting.
* De-duplication happens globally across all visitors. If visitor A sends `event1:ABC` then visitor B also sends `event1:ABC`, Adobe ignores the second instance from visitor B.
* De-duplication does not expire. If a visitor sends `event1:ABC` then comes back 2 years later and sends `event1:ABC` again, Adobe ignores the second instance.

> [!TIP] If you want to de-duplicate the `purchase` event, use the `purchaseID` variable instead.

## Use event IDs in Adobe Experience Platform Launch

You can set the event ID field either while configuring the Analytics extension (global variables) or as an action in a rule.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Events] section, where each event contains an [!UICONTROL Event ID] field.

Valid values are alpha-numeric characters up to 20 bytes in length.

## Use event IDs in AppMeasurement and Launch custom code editor

Event serialization is part of the `s.events` variable. Assign an ID to each event using a colon in the string.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

If an event has serialization enabled but does not contain a serialization ID, the event is always counted.
