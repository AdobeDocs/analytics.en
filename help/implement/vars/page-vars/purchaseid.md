---
description: Learn about the purchaseID variable, which helps prevent duplicate purchases from appearing in Adobe Analytics.
keywords: duplicate,purchase,purchaseid,s.purchaseid
subtopic: Variables
title: purchaseID
topic:
uuid:
---

# purchaseID

The `purchaseID` variable is used to keep an order from being counted multiple times in reporting. Whenever the purchase event is used on your site, Adobe recommends using the `purchaseID` variable.

When a visitor purchases an item from your site, `purchaseID` is typically populated on the "Thank You" or "Order Confirmation" page. Set the `purchaseID` variable at the same time a purchase event is fired. When `purchaseID` is defined to a unique value, conversion variable values only count for hit with that unique purchase ID. Defining the `purchaseID` is valuable because visitors commonly bookmark a purchase confirmation page for their own purposes. If your implementation does not use `purchaseID`, conversion data (such as revenue) can easily inflate by visitors refreshing pages.

In addition to purchase data, all conversion variables and events are not counted multiple times for hits with the same purchase ID.

Specific server-side code can be used to generate the unique number (alphanumeric value) embedded in the HTML source. Usually the Order ID, or similar alphanumeric value, is used for this purpose. This value should not change if the user refreshes the page.

## Syntax

The `purchaseID` variable can hold any alpha-numeric value, up to a maximum of 20 bytes. If you set a purchase ID longer than 20 bytes, the value is truncated.

```js
s.purchaseID = "uniqueid";
```

* Do not use a JavaScript randomization function to generate a number, which generates unique numbers each time the page is loaded. Adobe recommends using a data layer to store a given purchase ID.
* The unique identifiers are applicable to all users across all sessions. Make sure all purchase ID's are truly unique.
* Valid values are alphanumeric values up to 20 characters in length.
* The `s.purchaseID` variable serializes all events passed in the `s.events` variable, and overrides any serialization value for events. Do not use [!UICONTROL Event serialization] for any events if the `s.purchaseID` variable is used on the current page.
* If the `s.purchaseID` variable is left blank, each instance of the purchase event, even page reloads, is counted.
