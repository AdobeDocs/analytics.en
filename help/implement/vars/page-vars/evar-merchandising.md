---
title: eVar (Merchandising) variables
description: Custom variables that tie to individual products.
feature: Variables
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
---
# eVar (Merchandising)

*This help page describes how to implement merchandising eVars. For information on how merchandising eVars work as a dimension, see [eVars (Merchandising)](/help/components/dimensions/evar-merchandising.md) in the Components user guide.*

For a detailed discussion of how merchandising eVars work, see [Merchandising eVars and product finding methods](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=en).

## Set up eVars in report suite settings

Before using eVars in your implementation, make sure you configure the eVar to the desired syntax in report suite settings. See [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

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

### Using XDM for Edge Collection

Each field in the 'products' variable is populated by a corresponding XDM field. You can see a list of all mappings from XDM to Analytics parameters [here](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en). Below is an example illustrating how the productListItems XDM fields are combined to create a products variable.

XDM structure:

```js
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

Resulting 'products' parameter passed in to Analytics:

```js
pl = ”;Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large”
```

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

### Using XDM for Edge Collection

You can specify the same information using XDM fields that are mapped to Analytics fields. You can see a list of all mappings from XDM to Analytics parameters [here](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en). The XDM mirroring the example above would look like the following:

Set the eVar on the same or previous event call:

```js
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

```js
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
