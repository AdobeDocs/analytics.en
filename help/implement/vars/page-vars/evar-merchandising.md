---
title: eVar (Merchandising variable)
description: Custom variables that tie to individual products.
feature: Appmeasurement Implementation
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/BdChWcR9AJqLZ0KjOxSvFAjB8-58JmmGahrpvTyFeFI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# eVar (Merchandising)

>[!BEGINSHADEBOX]

*This help page describes how to implement merchandising eVars. For information on how merchandising eVars work as a dimension, see [eVar (Merchandising dimension)](/help/components/dimensions/evar-merchandising.md) in the Components user guide.*

>[!ENDSHADEBOX]

Merchandising eVars bind a value to individual products, so that success events involving each product are credited to the value bound to that product. You can set the value in one of two ways:

* **[!UICONTROL Product Syntax]**: Set the value on each product in the [`products`](products.md) variable.
* **[!UICONTROL Conversion Variable Syntax]**: Set the value in the eVar itself. The value binds to the products on a hit that contains a binding event.

For how binding, allocation, and expiration work, see [eVar (Merchandising dimension)](/help/components/dimensions/evar-merchandising.md).

## Set up eVars in report suite settings

Before using eVars in your implementation, make sure that you configure the eVar to the desired syntax in report suite settings. See [Conversion variables](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

>[!WARNING]
>
>Failure to correctly configure merchandising eVars results in unexpected values or data loss for the variable. Make sure it is correctly configured for your implementation.

## Choose a syntax

Use [!UICONTROL Product Syntax] when the merchandising value is available at the time you set the `products` variable, or when products in the same hit need different values. Use [!UICONTROL Conversion Variable Syntax] when the value is known before the product, such as the search term or internal campaign that led the visitor to the product. See [How binding and allocation work](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work) for a full comparison.

## Implement using product syntax

When [!UICONTROL Product Syntax] is enabled, the merchandising value is set directly within the `products` variable, so binding events are not used. Merchandising eVars go in the last segment of each product:

```js
s.products = "[category];[name];[quantity];[revenue];[events];[eVars]";
```

Delimit multiple merchandising eVars on the same product with a pipe (`|`). The empty placeholders for quantity, revenue, and events are required even if you don't use them. Without them, the eVar value is ignored.

The value is bound to the product on that hit. Whether a later value replaces an existing binding depends on the [!UICONTROL Allocation] setting. See [How binding and allocation work](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work).

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

### Product syntax using the Web SDK

If using the [**XDM object**](/help/implement/aep-edge/xdm-var-mapping.md), product syntax merchandising variables use the following XDM fields:

* Product syntax merchandising eVars are mapped under `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar1` to `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar250`.
* Product syntax merchandising events are mapped under `xdm.productListItems[]._experience.analytics.event1to100.event1.value` to `xdm.productListItems[]._experience.analytics.event901to1000.event1000.value`. [Event serialization](events/event-serialization.md) XDM fields are mapped under `xdm.productListItems[]._experience.analytics.event1to100.event1.id` to `xdm.productListItems[]._experience.analytics.event901to1000.event1000.id`.

>[!NOTE]
>
>When you set events under `productListItems`, you do not need to set them in the event string. If they are set in both places, the value in the event string takes precedence.

The following example shows a single [product](products.md) using multiple merchandising eVars and events:

```json
"productListItems": [
  {
    "name": "Bahama Shirt",
    "priceTotal": "12.99",
    "quantity": 3,
    "_experience": {
      "analytics": {
        "customDimensions" : {
          "eVars" : {
            "eVar10" : "green",
            "eVar33" : "large"
          }
        },
        "event1to100" : {
          "event4" : {
            "value" : 1
          },
          "event10" : {
            "value" : 2,
            "id" : "abcd"
          }
        }
      }
    }
  }
]
```

The above example object would be sent to Adobe Analytics as `";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"`.

If using the [**data object**](/help/implement/aep-edge/data-var-mapping.md), product syntax merchandising eVars are set in `data.__adobe.analytics.products`, using the same syntax as the AppMeasurement `products` variable. The data object equivalent of the XDM example above:

```json
"data": {
  "__adobe": {
    "analytics": {
      "products": ";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"
    }
  }
}
```

## Implement using conversion variable syntax

Use [!UICONTROL Conversion Variable Syntax] when the eVar value is not available to set in the `products` variable. This scenario typically means that your product page has no context of the merchandising channel or finding method. In these cases, set the merchandising eVar on or before the page where the binding event occurs. The value persists until it expires or is overwritten with a new value.

When a hit contains both the `products` variable and a selected [!UICONTROL Merchandising Binding Event], the eVar's current value binds to every product on that hit. Setting the eVar alongside a product without a binding event does not bind the value. Whether a later binding replaces an existing one depends on the [!UICONTROL Allocation] setting. See [How binding and allocation work](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work).

For an example that sets several product finding method eVars at once, see [Best practice: product finding methods](/help/components/dimensions/evar-merchandising.md#best-practice-product-finding-methods).

The following example sets a merchandising eVar before the binding event:

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

If [!UICONTROL Product View Event] is a binding event, the value `"Aviary"` for `eVar1` is bound to the product `"Canary"`. Subsequent success events that involve this product are credited to `"Aviary"`. The value `"Aviary"` also binds to products on later hits that contain a binding event, until one of the following conditions is met:

* The eVar expires (based on the [!UICONTROL Expire After] setting).
* The merchandising eVar is overwritten with a new value.

### Conversion variable syntax using the Web SDK

If using the [**XDM object**](/help/implement/aep-edge/xdm-var-mapping.md), syntax operates similarly to implementing other [eVars](evar.md) and [events](events/events-overview.md). If using the [**data object**](/help/implement/aep-edge/data-var-mapping.md), syntax follows AppMeasurement.

The XDM mirroring the AppMeasurement example above would look like the following.

Set the eVar on the same or previous event call:

```json
"_experience": {
  "analytics": {
    "customDimensions": {
      "eVars": {
        "eVar1" : "Aviary"
      }
    }
  }
}
```

Set the binding event and values for the products string:

```json
"commerce": {
  "productViews" : {
    "value" : 1
  }
},
"productListItems": [
  {
    "name": "Canary"
  }
]
```

The data objects mirroring the AppMeasurement example above would look like the following.

Set the eVar on the same or previous event call:

```json
"data": {
  "__adobe": {
    "analytics": {
      "eVar1": "Aviary"
    }
  }
}
```

Set the binding event and values for the products string:

```json
"data": {
  "__adobe": {
    "analytics": {
      "events": "prodView",
      "products": ";Canary"
    }
  }
}
```

