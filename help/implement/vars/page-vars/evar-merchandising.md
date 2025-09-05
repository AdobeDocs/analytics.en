---
title: eVar (Merchandising variable)
description: Custom variables that tie to individual products.
feature: Appmeasurement Implementation
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
---
# eVar (Merchandising)

*This help page describes how to implement merchandising eVars. For information on how merchandising eVars work as a dimension, see [eVars (Merchandising dimension)](/help/components/dimensions/evar-merchandising.md) in the Components user guide.*

For a detailed discussion of how merchandising eVars work, see [Merchandising eVars and product finding methods](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md).

## Set up eVars in report suite settings

Before using eVars in your implementation, make sure that you configure the eVar to the desired syntax in report suite settings. See [Conversion variables](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

>[!WARNING]
>
>Failure to correctly configure merchandising eVars results in unexpected values or data loss for the variable. Make sure it is correctly configured for your implementation.

## Implement using product syntax

When 'Product Syntax' is enabled, the merchandising category is populated directly within the `products` variable, so selecting and setting a binding event is not required. This is the recommended method and should be used unless the value is not available to set in `products` when the success event takes place.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

The value for `eVar1` is assigned to the product. All subsequent success events that involve this product are credited to the eVar value.

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

If using the [**data object**](/help/implement/aep-edge/data-var-mapping.md), eVar merchandising uses `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` following AppMeasurement syntax.

## Implement using conversion variable syntax

Conversion Variable Syntax is used when the eVar value is not available to set in the `products` variable. This scenario typically means that your page has no context of the merchandising channel or finding method. In these cases you set the merchandising variable before you arrive at the product page, and the value persists until the binding event occurs.

When the binding event selected during configuration occurs, the persisted value of the eVar is associated with the product. For example, if `prodView` is specified as the binding event, the merchandising category is tied to the current product list only at the time the event occurs. Only subsequent binding events can update a merchandising eVar that has already been assigned to a product.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

The value `"Aviary"` for `eVar1` is assigned to the product `"Canary"`. All subsequent success events that involve this product are credited to `"Canary"`. Additionally, the current value of the merchandising variable is tied to all subsequent products until one of the following conditions is met:

* The eVar expires (based on the 'Expire After' setting)
* The merchandising eVar is overwritten with a new value.

### Conversion variable syntax using the Web SDK

If using the [**XDM object**](/help/implement/aep-edge/xdm-var-mapping.md), syntax operates similarly to implementing other [eVars](evar.md) and [events](events/events-overview.md). The XDM mirroring the example above would look like the following:

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

If using the [**data object**](/help/implement/aep-edge/data-var-mapping.md), the data objects mirroring the example above would look like the following:

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
