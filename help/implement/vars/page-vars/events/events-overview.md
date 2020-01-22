---
title: events
description: Set the events variable, which governs most metrics on your site.
---

# events

Dimensions and metrics are vital components to reports. The `events` variable is responsible for data collection of many metrics on your site.

## Events in Adobe Experience Platform Launch

You can set events either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Events] section.

Several features are available:

* A dropdown allows you to select the event to include
* An optional text field for serialization. See [event serialization](event-serialization.md) for more information.
* An optional text field for an event value. You can include currency for currency events, or an integer for non-currency events to increment it multiple times. For example, selecting `event1` under the dropdown and including `10` in this field increments `event1` by 10 in reporting.
* A button to add another event. There is not a reasonable limit to the number of events you can include in a hit.

## s.events in AppMeasurement and Launch custom code editor

The `s.events` variable is a string that contains a comma-delimited list of events to include in the hit. There is no byte limit for this variable, so it does not get truncated. Valid values include:

* `event1` - `event1000`: Custom events, set however you'd like. Record how you use each event in your organization's [solution design document](../../../prepare/solution-design.md). The number of available events depends on your organization's Analytics contract. Most organizations on non-legacy contracts have 1000 custom events available. Contact your organization's account manager if you are not sure how many custom events are available to you.
* `purchase`: Increments the 'Orders' metric by 1, and takes values set in the `products` variable to calculate 'Units' and 'Revenue'. See [purchase event](event-purchase.md) for more information.
* `prodView`: Increments the 'Product Views' metric.
* `scOpen`: Increments the 'Carts' metric.
* `scAdd`: Increments the 'Cart Additions' metric.
* `scRemove`: Increments the 'Cart Removals' metric.
* `scView`: Increments the 'Cart Views' metric.
* `scCheckout`: Increments the 'Checkouts' metric.

> [!TIP] This variable is case-sensitive. Avoid mis-capitalizing event values to ensure accurate data collection.

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### Increment counter events multiple times

You can count custom events more than once if desired. Assign an integer to the desired event within the string. Events created in report suite settings are counter events by default.

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

> [!NOTE] Counter events do not support currency or decimal values. Use currency events for currency, or numeric events for decimal values.

### Use currency events

You can change a custom event to use currency instead of integers. Currency events automatically convert to the report suite's currency if the report suite currency and the `currencyCode` variable do not match. They are useful to help calculate shipping costs, discounts, or refunds. You can set currency events in the `products` variable if you want to attribute the event to only that product.

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

> [!NOTE] If you set a currency value in both the `events` variable and the `products` variable, the currency value in `events` is used. Avoid setting currency values in both the `events` and `products` variables.

### Use numeric events

You can change a custom event accept decimal values instead of integers. Numeric events behave similarly to currency events, except they do not use currency conversion. You can set numeric events in the `products` variable if you want to attribute the event to only that product.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

> [!NOTE] If you set a numeric value in both the `events` variable and the `products` variable, the numeric value in `events` is used. Avoid setting numeric values in both the `events` and `products` variables.
