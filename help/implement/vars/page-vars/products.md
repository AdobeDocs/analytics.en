---
title: products
description: Send data around what product(s) are displayed or in the cart.
feature: Variables
exl-id: f26e7c93-f0f1-470e-a7e5-0e310ec666c7
---
# products

The `products` variable tracks products and properties tied to them. This variable is typically set on individual product pages, shopping cart pages, and purchase confirmation pages. It is a multi-value variable, meaning you can send multiple products in the same hit and Adobe parses the value into separate dimension items.

>[!NOTE]
>
>If this variable is set in a hit without the [`events`](events/events-overview.md) variable, the [Product Views](/help/components/metrics/product-views.md) metric increments by 1. Make sure that you set the appropriate events on each hit with the `products` variable.

## Products using the Web SDK

Products are [mapped for Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under several XDM fields:

* Category is mapped to `productListItems[].lineItemId`.
* Product is mapped to `productListItems[].SKU` or `productListItems[].name`. If both XDM fields are present, `productListItems[].SKU` is used.
* Quantity is mapped to `productListItems[].quantity`.
* Price is mapped to `productListItems[].priceTotal`.
* Merchandising eVars are mapped to `productListItems._experience.analytics.customDimensions.eVars.eVar1` to `productListItems._experience.analytics.customDimensions.eVars.eVar250`, depending on which eVar you want to bind to a product.
* Merchandising events are mapped to `productListItems[]._experience.analytics.event1to100.event1.value` to `productListItems._experience.analytics.event901to1000.event1000.value`, depending on which event that you want to bind to a product. Note that if an event is set under productListItems (e.g. productListItems._experience.analytics.event1) an entry in the event string will also be added, unless one is already specified (e.g.  (_experience.analytics.event1.value) . 

>[!NOTE]
>
>`lineItemId` needs to be added as a custom field as it is not yet part of the standard Analytics Event schema. Adobe plans to add a dedicated 'Category' field in the future.

## Products using the Adobe Analytics extension

There is not a dedicated field in Adobe Experience Platform Data Collection to set this variable; however, multiple third-party extensions exist to help.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Extensions] tab, then click [!UICONTROL Catalog] to see all available extensions.
4. Search for the term "product", which reveals several extensions available to help set this variable.

You can use one of these extensions, or you can use the custom code editor following AppMeasurement syntax below.

## s.products in AppMeasurement and the Analytics extension custom code editor

The `s.products` variable is a string that contains multiple delimited fields per product. Delimit each field with a semicolon (`;`) in the string.

* **Category** (optional): The product category. The maximum length for this field is 100 bytes.
* **Product name** (required): The name of the product. The maximum length for this field is 100 bytes.
* **Quantity** (optional): How many of this product is in the cart. This field only applies to hits with the purchase event.
* **Price** (optional): The total price of the product as a decimal. If quantity is more than one, set price to the total and not the individual product price. Align the currency of this value to match the [`currencyCode`](../config-vars/currencycode.md) variable. Do not include the currency symbol in this field. This field only applies to hits with the purchase event.
* **Events** (optional): Events tied to the product. Delimit multiple events with a pipe (`|`). See [events](events/events-overview.md) for more information.
* **eVars** (optional): Merchandising eVars tied to the product. Delimit multiple merchandising eVars with a pipe (`|`). See [merchandising eVars](evar-merchandising.md) for more information.

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

This variable supports multiple products in the same hit. It is valuable for shopping cart and purchases containing multiple products. The maximum length for the entire `products` string is 64K. Separate each product with a comma (`,`) in the string.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2;1;5.99";
```

>[!WARNING]
>
>Strip all semicolons, commas, and pipes from product names, categories, and merchandising eVar values. If a product name includes a comma, AppMeasurement parses it as the start of a new product. This incorrect parsing throws off the rest of the product string, causing incorrect data in dimensions and reports.

## Examples

The `products` variable is flexible when omitting fields and including multiple products. This flexibility can make it easy to miss a delimiter, which causes your implementation to send incorrect data to Adobe.

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product 1,;Example product 2";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = ";Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = ";Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = ";Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = ";Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = ";Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```

If using the `digitalData` [data layer](../../prepare/data-layer.md), you can iterate through the `digitalData.product` object array:

```js
for(var i = 0; i < digitalData.product.length; i++) {
    // Add individual product info to the product string
    s.products += digitalData.product[i].category.primaryCategory + ";" + digitalData.product[i].productInfo.productName;
    // If there are more products, add a comma
    if(i != digitalData.product.length - 1) {
        s.products += ",";
    }
}
```
