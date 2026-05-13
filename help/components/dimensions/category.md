---
title: Category
description: The product category of the hit.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
TQID: https://experienceleague.adobe.com/3G1qDbtVnRj8At-FU1fNaI8KLboMQvo8NKktinrTbs8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Category

The 'Category' [dimension](overview.md) reports the product category of the hit. It is useful for implementations that use the `products` variable and want to see metrics around product category, such as top sellers or most viewed. This dimension can intentionally be blank if you don't have any products on your site.

## Populate this dimension with data

This dimension references the first part of the string in the [`products`](/help/implement/vars/page-vars/products.md) variable. Everything before the first semicolon (`;`) populates this dimension.

## Dimension items

Since this variable is based on a custom string in your implementation, your organization determines what the dimension items are. Adobe recommends that you group individual products into meaningful categories, using both the 'Product' and 'Category' dimensions.

>[!TIP]
>
>In previous versions of Adobe Analytics, some limitations to the 'Category' dimension were imposed due to its processing architecture. Those limitations have since been removed, allowing you to use any metric and any breakdown.
