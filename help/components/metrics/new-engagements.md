---
title: New engagements
description: The number of times a first touch channel is set.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
TQID: https://experienceleague.adobe.com/UsPu31wUqpoDYQy5aT9wnzSUgJ6i9mHVZ8pAtFQgzGo
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
# New engagements

The 'New engagements' [metric](overview.md) shows the number of times a visitor matches a marketing channel for the first time in that visitor's engagement period. This metric is useful when you want to compare any dimension with a visitor matching a marketing channel processing rule for the first time.

## How this metric is calculated

During data processing, every hit runs through [Marketing channel processing rules](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md). If a hit matches any marketing channel processing rule and the visitor does not already have a first touch channel, the hit is a new engagement. If a hit does not match any marketing channel processing rules or if the visitor already has a first touch channel, the hit is not a new engagement.

Visitors can have more than one new engagement if they let their visitor engagement period expire.
