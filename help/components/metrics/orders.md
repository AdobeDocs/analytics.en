---
title: Orders
description: The number of purchases made.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
TQID: https://experienceleague.adobe.com/jRd-oUTfcJXACj-mkEyzRm8k-rxcVCxe7U3lROIy7DQ
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
# Orders

The 'Orders' [metric](overview.md) shows the total number of purchase events made on your site. This metric is vital for eCommerce sites in measuring conversion. You can combine this metric with any dimension to see which dimension items contributed to an order. For example, you could see the top campaigns (using the [Tracking code](../dimensions/tracking-code.md) dimension) or top internal search terms (using an [eVar](../dimensions/evar.md)) that contributed to purchases.

## How this metric is calculated

This metric counts the number of hits where `purchase` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.
