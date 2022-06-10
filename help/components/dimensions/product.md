---
title: Product
description: The name of the product.
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
---
# Product

The 'Product' dimension reports the name of the product in the hit. It is useful for implementations that use the `products` variable and want to see metrics around products, such as top sellers or most viewed. This dimension can intentionally be blank if you don't have any products on your site.

## Populate this dimension with data

This dimension references the second part of the string in the [`products`](/help/implement/vars/page-vars/products.md) variable. Characters between the first and second semicolon (`;`) populates this dimension.

## Dimension items

Since this variable is based on a custom string in your implementation, your organization determines what the dimension items are. Adobe recommends that you establish a consistent naming convention for products. [Classifications](../classifications/c-classifications.md) are available if you want to group products differently or provide a more friendly name. Adobe recommends using both the 'Product' and 'Category' dimensions.
