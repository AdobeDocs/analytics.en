---
title: Event serialization
description: Help deduplicate metrics on your site.
feature: Variables
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
---
# Event ID serialization

Event serialization is the process of implementing measures to prevent duplicate events from entering Analytics reporting. De-duplicating events is important in cases where you don't want metrics inflated by visitors refreshing the page.

>[!NOTE]
>
>Data Sources does not support event serialization or de-duplication.

## Set up event serialization

You must first set an event's [!UICONTROL Unique Event Recording] to [!UICONTROL Use Event ID] in report suite settings. See [Success Events](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) in the Admin user guide.

When using event IDs, de-duplication happens on the following levels:

* Each variable uses their own table for de-duplication. For example, `event1:ABC` and `event2:ABC` are both counted in reporting.
* De-duplication happens globally across all visitors. If visitor A sends `event1:ABC` then visitor B also sends `event1:ABC`, Adobe ignores the second instance from visitor B.
* De-duplication does not expire. If a visitor sends `event1:ABC` then comes back 2 years later and sends `event1:ABC` again, Adobe ignores the second instance.

>[!TIP]
>
>If you want to de-duplicate the [`purchase`](event-purchase.md) event, use the [`purchaseID`](../purchaseid.md) variable instead.

## Use event IDs using the Web SDK

Event serialization is [mapped for Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under the desired event XDM field's `id`. The full XDM path depends on which event that you want to serialize.

For example, if you wanted to serialize the Cart Additions metric, set the `commerce.productListAdds.id` XDM field to the desired serialization value. If you wanted to serialize Custom event 20, set the `_experience.analytics.event1to100.event20` XDM field to the desired serialization value.

## Use event IDs using the Adobe Analytics extension

You can set the event ID field either while configuring the Analytics extension (global variables) or as an action in a rule.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Events] section, where each event contains an [!UICONTROL Event ID] field.

Valid values are alpha-numeric characters up to 20 bytes in length. If you enter a value that is longer than 20 bytes, then the system truncates it to the first 20 bytes.

## Use event IDs in AppMeasurement and the Analytics extension custom code editor

Event serialization is part of the `s.events` variable. Assign an ID to each event using a colon in the string.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

If an event has serialization enabled but does not contain a serialization ID, the event is always counted.
