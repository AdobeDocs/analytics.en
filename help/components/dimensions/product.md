---
title: Product
description: The name of the product.
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
TQID: https://experienceleague.adobe.com/SMFFeSTkQyQoSWNFc8qHJRxYkJQmiJoKd0v4rS6xRKc
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
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Product

The 'Product' [dimension](overview.md) reports the name of the product in the hit. It is useful for implementations that use the `products` variable and want to see metrics around products, such as top sellers or most viewed. This dimension can intentionally be blank if you don't have any products on your site.

## Populate this dimension with data

This dimension references the second part of the string in the [`products`](/help/implement/vars/page-vars/products.md) variable. Characters between the first and second semicolon (`;`) populates this dimension.

## Dimension items

Since this variable is based on a custom string in your implementation, your organization determines what the dimension items are. Adobe recommends that you establish a consistent naming convention for products. [Classifications](../classifications/classifications-overview.md) are available if you want to group products differently or provide a more friendly name. Adobe recommends using both the 'Product' and 'Category' dimensions.
