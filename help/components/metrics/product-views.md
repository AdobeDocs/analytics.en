---
title: Product views
description: The number of views to product pages.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
TQID: https://experienceleague.adobe.com/bspBkiEAfkwBQwWV3-KoDKDRNGLogCKkSXvY2Cpyv-M
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
# Product views

The 'Product views' [metric](overview.md) shows the number of times any product was viewed. This metric is useful when you want to see your top-viewed products, or see how total product views trend over time.

## How this metric is calculated

This metric counts the number of hits that match **either** of the following:

* The value `prodView` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable; or
* The [`products`](/help/implement/vars/page-vars/products.md) variable is set, and the `events` variable is empty.
