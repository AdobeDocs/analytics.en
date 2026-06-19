---
title: Experience Cloud Visitor ID
description: The Experience Cloud ID (ECID) of the visitor, available in Data Warehouse.
feature: Dimensions
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
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Experience Cloud Visitor ID

The 'Experience Cloud Visitor ID' [dimension](overview.md) provides the Experience Cloud ID (ECID) for each visitor. It is a 128-bit number consisting of two concatenated 64-bit numbers padded to 19 digits.

>[!IMPORTANT]
>
>This dimension is only available in Data Warehouse.

## Populate this dimension with data

This dimension requires an implementation that uses the Experience Cloud ID Service (ECID). It corresponds to the `mcvisid` column in data feeds. See [Data column reference](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) for more information.

## Dimension items

Dimension items include the Experience Cloud ID of each visitor.
