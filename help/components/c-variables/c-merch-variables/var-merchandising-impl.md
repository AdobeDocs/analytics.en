---
description: Describes how to enable and implement a merchandising variable.
keywords: Analytics Implementation;merchandising;variable;product syntax;Conversion Variable Syntax;s.products
solution: Analytics
title: Implement a merchandising variable
topic: Developer and implementation
---

# Implement a merchandising variable

Describes how to enable and implement a merchandising variable.

## Enable a Merchandising Variable

Merchandising can be enabled for any custom eVar under **[!UICONTROL Admin Tools]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Conversion Variables]**.

![](assets/merch-enable.png)

| Setting | Description |
|--- |--- |
| Expire After | Determines how long merchandising values should persist. |
| Merchandising | **Product Syntax:** The value is set within `s.products`.<br>**Conversion Variable Syntax:** The value is set in the designated merchandising eVar. |
| Merchandising Binding Event (Conversion variable syntax only) | Indicates when a product should be tied to the current merchandising category. Multiple events can be selected by holding down Ctrl and clicking on multiple items in the list. You can select an event only when the "Conversion Variable Syntax" is selected. |

## Implementing Using Product Syntax

When Product Syntax is enabled, the merchandising category is populated directly within the products variable, so selecting and setting a binding event is not required. This is the recommended method and should be used unless the value is not available to set in `s.products` when the success event takes place.

### Syntax

```js
s.products="category;product;quantity;price;event_incrementer;eVarN=merch_category|eVarM=merch_category2";
```

### Example

```js
s.events="prodView";
s.products=";Snow Goggles;;;;eVar1=goggles";
```

The value "goggles" for eVar1 is assigned to the product "Snow Goggles". All subsequent success events (product adds, checkouts, purchases, and so on) that involve this product are credited to "goggles".

## Implementing Using Conversion Variable Syntax

Conversion Variable Syntax should be used when the eVar value is not available to set in `s.products`. This typically means that your page has no context of the merchandising channel or finding method. In these cases you must set the merchandising variable before you arrive at the product page, and the value persists until the binding event occurs.

When the binding event selected during configuration occurs, the persisted value of the eVar is associated with the product. For example, if prodView is specified as the binding event, the merchandising category is tied to the current product list only at the time the event occurs. Only subsequent binding events can update a merchandising eVar that has already been assigned to a product.

### Syntax

Place on the same or previous page before the binding event:

```js
s.eVar1="merchandising_category";
```

Place on the page where the binding event occurs:

```js
s.events="prodView";
s.products="category;product";
```

### Example

On page 1 of the visit:

```js
s.eVar1="Outdoors"
```

On page 2 of the visit:

```js
s.events="prodView";
s.products=";Snow Goggles";
```

The value "Outdoors" for eVar1 is assigned to the product "Snow Goggles". All subsequent success events (product adds, checkouts, purchases, and so on) that involve this product are credited to "Snow Goggles". Additionally, the current value of the merchandising variable is tied to all subsequent products until one of the following conditions is met:

* eVar expires (based on the "Expire After" setting)
* The merchandising eVar is overwritten with a new value.

## External additional information

[Advanced Conversion Syntax Merchandising](https://analyticsdemystified.com/adobe-analytics/advanced-conversion-syntax-merchandising/) on [!DNL analyticsdemystified.com]
