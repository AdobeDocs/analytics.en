---
title: purchaseID
description: Deduplicate hits based on a unique purchase identifier.
---

# purchaseID

The `purchaseID` variable helps prevent hits containing the same purchase from inflating reports. For example, if a visitor reaches your purchase confirmation page, you typically send data around the revenue generated from the transaction to Adobe. If the user refreshes this page multiple times or bookmarks the page to visit later, those hits can inflate reports. The `purchaseID` variable de-duplicates metrics when more than one hit has the same purchase ID.

When Adobe recognizes a hit as a duplicate purchase, all conversion data (such as eVars and events) do not show in reporting. In data feeds, the `duplicate_purchase` column is set to `1`.

Purchase ID's apply to all visitors and do not expire. If one visitor sets a given purchase ID, then a different visitor sets that same purchase ID a year later, the second purchase is de-duplicated.

## Purchase ID in Adobe Experience Platform Launch

There is not a dedicated field in Launch to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.purchaseID in AppMeasurement and Launch custom code editor

The `s.purchaseID` variable is a string that contains a unique identifier to a purchase. It is set on the same hit as a purchase event. Only use alpha-numeric characters to populate this variable.

This variable can store a maximum of 20 bytes; values longer than 20 bytes are truncated. If this truncated value matches subsequent truncated values, those subsequent hits are de-duplicated.

```js
s.purchaseID = "ABC123";
```

> [!NOTE] Do not use a randomization function to generate a purchase ID. Adobe recommends using a [data layer](../../prepare/data-layer.md) to store a given purchase ID.
