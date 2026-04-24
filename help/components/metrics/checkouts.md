---
title: Checkouts
description: The number of hits where a visitor started the checkout process.
feature: Metrics
exl-id: 747f2244-efc6-473f-bc0c-a5898cc8a717
TQID: https://experienceleague.adobe.com/w74KqGe1B9dE2A0-ZQy-P8gOybBbF1UtuP8RuZMNVy8
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
# Checkouts

The 'Checkouts' [metric](overview.md) shows the number of times a visitor started the checkout process. This metric is helpful when you want to understand the part of the conversion funnel where customers have a cart of products and are ready to purchase them.

## How this metric is calculated

This metric counts the number of hits where `scCheckout` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.
