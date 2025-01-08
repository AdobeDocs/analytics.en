---
title: purchaseID
description: Deduplicate hits based on a unique purchase identifier.
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
---
# purchaseID

The `purchaseID` variable helps prevent hits containing the same purchase from inflating reports. For example, if a visitor reaches your purchase confirmation page, you typically send data around the revenue generated from the transaction to Adobe. If the user refreshes this page multiple times or bookmarks the page to visit later, those hits can inflate reports. The `purchaseID` variable de-duplicates metrics when more than one hit has the same purchase ID.

When Adobe recognizes a hit as a duplicate purchase, all conversion data (such as eVars and events) do not show in reporting. In data feeds, the `duplicate_purchase` column is set to `1`.

Purchase ID's apply to all visitors and expire after 37 months. If one visitor sets a given purchase ID, then a different visitor sets that same purchase ID a year later, the second purchase is de-duplicated.

## Purchase ID using the Web SDK

Purchase ID is mapped to the following variables:

* [XDM object](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.purchaseID`
* [Data object](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.purchaseID`

## Purchase ID using the Adobe Analytics extension

You can set purchase ID either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] drop-down list to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Purchase ID] section.

You can set purchase ID to a value or a data element. You can also copy the value from another Analytics variable.

## s.purchaseID in AppMeasurement and the Analytics extension custom code editor

The `s.purchaseID` variable is a string that contains a unique identifier to a purchase. It is set on the same hit as a purchase event. Only use alpha-numeric characters to populate this variable.

This variable can store a maximum of 20 bytes; values longer than 20 bytes are truncated. If this truncated value matches subsequent truncated values, those subsequent hits are de-duplicated.

```js
s.purchaseID = "ABC123";
```

If using the `digitalData` [data layer](../../prepare/data-layer.md):

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>Do not use a randomization function to generate a purchase ID.
