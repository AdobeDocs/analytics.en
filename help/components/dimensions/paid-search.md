---
title: Paid search
description: Distinguishes metrics from paid and natural search.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
TQID: https://experienceleague.adobe.com/s9jhjGeXaOCo-Wz-Jyof951NZdRWfz-9tjrVrjHvTS0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Paid search

The 'Paid search' [dimension](overview.md) lets you look at any metric and compare it between paid search and natural search. All other hits outside search engines are omitted. This dimension is helpful to understand how your paid search efforts compare with organic search.

## Populate this dimension with data

The only requirement for this dimension to work properly is to have [Paid search detection](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) configured correctly in report suite settings. If paid search detection is configured correctly and a report suite has data, this dimension always works.

## Dimension items

Dimension items include two static values: `"Natural"` and `"Paid"`. If a visit matches criteria for a search engine and also matches paid search detection, it belongs to the `"Paid"` dimension item. If a visit matches criteria for a search engine and does *not* match paid search detection, it belongs to the `"Natural"` dimension item.
