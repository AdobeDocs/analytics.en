---
title: Cart additions
description: The number of hits where a visitor added a product to their cart.
feature: Metrics
exl-id: 0617b4c4-6425-4425-b6f7-efadbd6f58b2
TQID: https://experienceleague.adobe.com/8qCXd6cm7VLZnEpClBYDjpaUJwLXcb1SG4v41OWiHtM
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
# Cart additions

The 'Cart additions' [metric](overview.md) shows the number of times a visitor added something to their cart. This metric is helpful when you want to understand the part of the conversion funnel where customers are interested enough in a product to add it to their cart. 

## How this metric is calculated

This metric counts the number of hits where `scAdd` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.

See [Carts](carts.md) for a metric comparison.

