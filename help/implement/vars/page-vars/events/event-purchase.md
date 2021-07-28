---
title: Purchase event
description: Use the purchase event to collect data for the 'Orders', 'Units', and 'Revenue' metrics.
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
---
# Purchase event

The purchase event is a value in the `events` variable. This value is useful for organizations that want to collect data around the revenue that their site generates. It is heavily dependent on the [`products`](../products.md) and [`purchaseID`](../purchaseid.md) variables.

When you set a purchase event, it affects the following metrics:

* The 'Orders' metric increments by 1
* The 'Units' metric increments by the number of products in the `products` variable
* The 'Revenue' metric increases by the sum of price parameters in the `products` variable

>[!NOTE]
>
>Revenue is not multiplied by the quantity field. For example, `s.products="Womens;Socks;5;4.50"` does not pass $22.50 into revenue; it passes $4.50. Make sure your implementation passes the total revenue for the quantity listed. For example,`s.products="Womens;Socks;5;22.50"`.

## Set the purchase event using tags in Adobe Experience Platform

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Events] section, and set the events dropdown to [!UICONTROL purchase].

Other dependent variables like `products` and `purchaseID` do not have dedicated fields in the Data Collection UI. Use the custom code editor following AppMeasurement syntax for these variables.

## Set the purchase event in AppMeasurement and custom code editor

The purchase event is a string that is set as part of the events variable.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Purchase event de-duplication

When you fire a purchase event, Adobe checks the following:

* Does the hit contain the `purchaseID` variable? If not, Adobe uses information from the hit to create a "temporary purchase ID". This temporary purchase ID only applies to the visitor of the hit. The previous 5 temporary purchase ID's are stored for each visitor ID per report suite.
* Does the temporary purchase ID match any of the last five stored temporary purchase IDs? If so, the image request is considered a duplicate purchase. All conversion variables, including the purchase event, do not appear in reporting.
* If the `purchaseID` variable is defined, does it match any value already collected in the report suite across all visitors? If so, the image request is considered a duplicate purchase. All conversion variables, including the purchase event, do not appear in reporting.
