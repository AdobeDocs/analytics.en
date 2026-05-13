---
title: Purchase event
description: Use the purchase event to collect data for the 'Orders', 'Units', and 'Revenue' metrics.
feature: Appmeasurement Implementation
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
role: Admin, Developer
TQID: https://experienceleague.adobe.com/r-L330P6HA5qWBmEW-2LwECo-d3dhVK1ovWsfraErXE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Purchase event

The purchase event is a value in the `events` variable. This value is useful for organizations that want to collect data around the revenue that their site generates. It is heavily dependent on the [`products`](../products.md) and [`purchaseID`](../purchaseid.md) variables.

When you set a purchase event, it affects the following metrics:

* The 'Orders' metric increments by 1
* The 'Units' metric increments by the number of products in the `products` variable
* The 'Revenue' metric increases by the sum of price parameters in the `products` variable

>[!NOTE]
>
>Revenue is not multiplied by the quantity field. For example, `s.products="Womens;Socks;5;4.50"` does not pass $22.50 into revenue; it passes $4.50. Make sure that your implementation passes the total revenue for the quantity listed. For example, `s.products="Womens;Socks;5;22.50"`.

## Set the purchase event using the Web SDK

If using the [**XDM object**](/help/implement/aep-edge/xdm-var-mapping.md), the purchase event uses the following XDM fields:

* Orders are mapped to `xdm.commerce.purchases.value`.
* Units are mapped to the sum of all `xdm.productListItems[].quantity` fields. See [`products`](../products.md) for more information.
* Revenue is mapped to the sum of all `xdm.productListItems[].priceTotal` fields.

```json
{
  "xdm": {
    "commerce": {
      "purchases": {
        "value": 1
      }
    }
  }
}
```

If using the [**data object**](/help/implement/aep-edge/data-var-mapping.md), the purchase event uses `data.__adobe.analytics.events`, following AppMeasurement string syntax.

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "events": "purchase"
      }
    }
  }
}
```

## Set the purchase event using the Adobe Analytics extension

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] drop-down list to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Events] section, and set the [!UICONTROL Events] drop-down list to [!UICONTROL purchase].

Other dependent variables like `products` and `purchaseID` do not have dedicated fields in the Analytics extension within Adobe Experience Platform Data Collection. Use the custom code editor following AppMeasurement syntax for these variables.

## Set the purchase event in AppMeasurement and the Analytics extension custom code editor

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
