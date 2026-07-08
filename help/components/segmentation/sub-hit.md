---
title: Sub-Hit Analysis
description: Learn how sub-hit analysis lets you filter individual products within a hit in Adobe Analytics, eliminating attribution bleed in product reports.
feature: Segmentation
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
    internal-label: Segment Builder
---
# Sub-hit analysis

{{release-limited-testing}}

Sub-hit analysis lets you analyze product data at a level more granular than the hit level. Instead of filtering on entire hits, you can segment on individual products within hits. For example, segmenting on a specific product category without including all other products purchased in the same order.

In Adobe Analytics sub-hit analysis applies specifically to the **[!UICONTROL Products]** variable. The **[!UICONTROL Products]** variable is the only multi-value object in Adobe Analytics that supports sub-hit analysis.

In Adobe Analytics, the [Products variable](/help/components/dimensions/product.md) can capture multiple products on a single hit. Without sub-hit analysis, segmenting on a product attribute returns all hits where any product within a hit matches the product attribute. The result is incorrect attribution and inflated revenue metrics. Sub-hit analysis scopes the filter to individual product rows within a hit and solves these issues.

In sub-hit analysis exclude logic behaves differently from standard hit-level exclusion against the Products variable. When you exclude product attributes within the [!UICONTROL Products] container, the segment returns hits that **have products** but don't match your exclusion criteria. The segment does not return hits with no products at all. 

## Example

You want to measure online revenue from the Men category only. Without sub-hit analysis, applying a segment for Men includes revenue from every product on any order (hit) that contains at least one product with the Men category. With sub-hit analysis, you scope the filter to the product level and return only revenue for products of the Men category.

You also want to measure online revenue from all other categories except the Men category.

>[!BEGINTABS]

>[!TAB Hit analysis]

In the segmentation builder or as part of a **[!UICONTROL Quick segment]**, you specify to **[!UICONTROL Include]** the **[!UICONTROL Dimension]** **[!UICONTROL Retail: Fashion Product Category]** **[!UICONTROL equals]** **[!UICONTROL Men]** on the **[!UICONTROL Hits]** container. 

![Panel showing segementation on hit level for product category Men](./assets/product-category-segmentation-hits.png)

As a result, all orders containing at least one **[!UICONTROL Men]** **[!UICONTROL Retail: Fashion Product Category]** are considered, and revenue from other products in those orders is included in the **[!UICONTROL Online Revenue]** metric.
When you report on categories, all other values for **[!UICONTROL Retail: Fashion Product Category]** are reported that were part of an order that included a product with the **[!UICONTROL Men]** **[!UICONTROL Retail: Fashion Product Category]**.

>[!TAB Sub-hit analysis]

In the segmentation builder or as part of a **[!UICONTROL Quick segment]**, you specify to **[!UICONTROL Include]** the **[!UICONTROL Dimension]** **[!UICONTROL Retail: Fashion Product Category]** **[!UICONTROL equals]** **[!UICONTROL Men]** on the **[!UICONTROL Products]** container. 

![Panel showing segementation on sub-hit level for product category Men](./assets/product-category-segmentation-sub-hits.png)

As a result, all orders containing at least a **[!UICONTROL Men]** **[!UICONTROL Retail: Fashion Product Category]** are considered, and only the revenue of products belonging to the **[!UICONTROL Men]** **[!UICONTROL Retail: Fashion Product Category]** are included for the **[!UICONTROL Online Revenue]** metric.
When you report on categories, only the **[!UICONTROL Men]** **[!UICONTROL Retail: Fashion Product Category]**  is reported.

>[!TAB Sub-hit analysis (exclude)]

In the segmentation builder or as part of a **[!UICONTROL Quick segment]**, you specify to **[!UICONTROL Exclude]** the **[!UICONTROL Dimension]** **[!UICONTROL Retail: Fashion Product Category]** **[!UICONTROL equals]** **[!UICONTROL Men]** on the **[!UICONTROL Products]** container. 

![Panel showing segementation on sub-hit level to exclude product category Men](./assets/product-category-segmentation-sub-hits-exclude.png)

To exclude at the product level, hits that contain at least one product are included, then the exclusion on sub-hit level is applied within that scope. This exclusion differs from hit-level exclusion, which excludes the entire hit.

>[!ENDTABS]
