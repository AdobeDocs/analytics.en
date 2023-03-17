---
title: New engagements
description: The number of times a first touch channel is set.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
---
# New engagements

The 'New engagements' metric shows the number of times a visitor matches a marketing channel for the first time in that visitor's engagement period. This metric is useful when you want to compare any dimension with a visitor matching a marketing channel processing rule for the first time.

## How this metric is calculated

During data processing, every hit runs through [Marketing channel processing rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md). If a hit matches any marketing channel processing rule and the visitor does not already have a first touch channel, the hit is a new engagement. If a hit does not match any marketing channel processing rules or if the visitor already has a first touch channel, the hit is not a new engagement.

Visitors can have more than one new engagement if they let their visitor engagement period expire.
