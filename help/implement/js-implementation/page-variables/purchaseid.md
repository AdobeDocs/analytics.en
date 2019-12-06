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

## Syntax

The `purchaseID` variable can hold any alpha-numeric value, up to a maximum of 20 bytes. If you set a purchase ID longer than 20 bytes, the value is truncated.

```js
s.purchaseID = "uniqueid";
```
