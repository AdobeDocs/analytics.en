---
title: Units
description: The total number of products purchased within all orders.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
TQID: https://experienceleague.adobe.com/0v4pF0Iv0IzU9K4CQiTy1-IIYgMCaO37E6QTmAAEPXc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
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
# Units

The 'Units' [metric](overview.md) shows the total number of products purchased within all orders. This metric is vital for eCommerce sites in measuring conversion. You can combine this metric with any dimension to see which dimension items contributed to how many products were purchased. For example, you could see the top campaigns (using the [Tracking code](../dimensions/tracking-code.md) dimension) or top internal search terms (using an [eVar](../dimensions/evar.md)) that contributed to products purchased.

## How this metric is calculated

For every hit where `purchase` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable, sum the 'Quantity' field within the [`products`](/help/implement/vars/page-vars/products.md) variable.

## Compare orders and units

The [Orders](orders.md) metric only records the number of purchase events. The 'Units' metric is typically higher than 'Orders' because customers can purchase more than one product. In these cases, a single order exists with multiple units.

If you have orders higher than units, Adobe recommends to check the integrity of your implementation. It is likely that your `products` variable is not set correctly on purchases, which is typically undesired behavior.
