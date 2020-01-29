---
title: products
description: Send data around what product(s) are displayed or in the cart.
---

# products

The `products` variable tracks products and properties tied to them. This variable is typically set on individual product pages, shopping cart pages, and purchase confirmation pages. It is a multi-value variable, meaning you can send multiple products in the same hit and Adobe parses the value into separate dimension values.

> [!NOTE] If this variable is set in a hit without a shopping cart event in the `events` variable, the 'Product Views' metric increments by 1. Make sure you set the appropriate shopping cart event on each hit.

## Products in Adobe Experience Platform Launch

There is not a dedicated field in Launch to set this variable; however, multiple third-party extensions exist to help.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click [!UICONTROL Catalog] to see all available extensions.
4. Search for the term "product", which reveals several extensions available to help set this variable.

You can use one of these extensions, or you can use the custom code editor following AppMeasurement syntax below.

## s.products in AppMeasurement and Launch custom code editor

The `s.products` variable is a string that contains multiple delimited fields per product. Each individual product can contain up to 100 bytes across all fields. Delimit each field with a semicolon (`;`) in the string.

* **Category** (optional): The overarching product category. Your organization decides how to group products into categories.
* **Product name** (required): The name of the product.
* **Quantity** (optional): How many of this product is in the cart. This field only applies to hits with the purchase event.
* **Price** (optional): The total price of the product as a decimal. If quantity is more than one, set price to the total and not the individual product price. Align the currency of this value to match the `currencyCode` variable. Do not include the currency symbol in this field. This field only applies to hits with the purchase event.
* **Events** (optional): Events tied to the product. Delimit multiple events with a pipe (`|`). See [events](events/events-overview.md) for more information.
* **eVars** (optional): Merchandising eVars tied to the product. Delimit multiple merchandising eVars with a pipe (`|`). See [merchandising eVars](../../../components/c-variables/c-merch-variables/var-merchandising.md) for more information.

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

This variable supports multiple products in the same hit. It is valuable for shopping cart and purchases containing multiple products. While there is a 100-byte limit per product, the total length for the `products` variable is 64K. Separate each product with a comma (`,`) in the string.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2,1,5.99";
```

> [!IMPORTANT] Make sure you strip all semicolons, commas, and pipes from product names, categories, and merchandising eVar values. If a product name includes a comma, AppMeasurement parses it as the start of a new product. This incorrect parsing throws off the rest of the product string, causing incorrect data in dimensions and reports.

## Examples

The `products` variable is flexible when omitting fields and including multiple products. This flexibility can make it easy to miss a delimiter, which causes your implementation to send incorrect data to Adobe.

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name if you do not want to use product category
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product,;Example product";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = "Example category;Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = "Example category;Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = "Example category 1;Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = "Example category;Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = "Example category;Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```
