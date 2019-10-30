---
description: The products variable is used for tracking products and product categories (as well as purchase quantity and purchase price).
keywords: Analytics Implementation;products variable;product view;success event
seo-description: The products variable is used for tracking products and product categories (as well as purchase quantity and purchase price).
seo-title: Detailed product view page
solution: Analytics
title: Detailed product view page
topic: Developer and implementation
uuid: 464c9daf-b042-4fb8-8ca6-e104c0bcef45
---

# Detailed product view page

The products variable is used for tracking products and product categories (as well as purchase quantity and purchase price).

 A success event should always be set in conjunction with the *`products`* variable.

```js
s.events="prodView"
```

> [!NOTE] While *`prodView`* is treated in implementation like an event, it does not have the same flexibility in the interface. The *`prodView`*event is an instance of the product and is only available in the *`products`* report. Adobe recommends you use a *`custom`* event in addition to the *`prodView`* event. This way, you can see the product view metrics alongside other metrics in other conversion reports.

```js
s.products=";diamond earrings (54321)"
```

> [!NOTE] The products string syntax must begin with a semicolon. This is a legacy syntax requirement. It was previously used to delimit the category and product, but that creates a limitation within the interface should you ever want to change how you are classifying products. For the maximum flexibility in your reporting, it is best to leave this blank and use Classifications to set up categories.

## Shopping Cart Page ( scOpen , scAdd , scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd"
s.products=";SKU"
```

## First Checkout Page {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout"
s.products=";SKU"
```

## Confirmation Page {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase"
s.products=";SKU"
```

> [!NOTE] While using the SKU in the product string may make the *`products`* report less readable, it provides the maximum flexibility later when you want to classify your products. You can create categories from the SKU that indicate finish, manufacturer, category, and sub-category.

When the *`products`* variable is set in conjunction with the *`purchase`* event, the purchase quantity and total purchase price are included in the products value as shown above.
