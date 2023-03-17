---
title: Category
description: The product category of the hit.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
---
# Category

The 'Category' dimension reports the product category of the hit. It is useful for implementations that use the `products` variable and want to see metrics around product category, such as top sellers or most viewed. This dimension can intentionally be blank if you don't have any products on your site.

## Populate this dimension with data

This dimension references the first part of the string in the [`products`](/help/implement/vars/page-vars/products.md) variable. Everything before the first semicolon (`;`) populates this dimension.

## Dimension items

Since this variable is based on a custom string in your implementation, your organization determines what the dimension items are. Adobe recommends that you group individual products into meaningful categories, using both the 'Product' and 'Category' dimensions.

>[!TIP]
>
>In previous versions of Adobe Analytics, some limitations to the 'Category' dimension were imposed due to its processing architecture. Those limitations have since been removed, allowing you to use any metric and any breakdown.
