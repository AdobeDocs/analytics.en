---
title: Entry dimensions
description: Lists entry dimensions and their use.
keywords: entry page, entry site section, entry server, entry custom insight
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
TQID: https://experienceleague.adobe.com/6a6Xy8SEqjcnuB1Acbwkesw6OA7Nggld5ppWtjYaj5k
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
---
# Entry dimensions

*This help page describes how entries work as a [dimension](overview.md). For information on how entries work as a metric, see the [Entries](../metrics/entries.md) metric.*

Entry dimensions are [visit-based](../metrics/visits.md). They record the first dimension item, and persist it for the entire duration of that visit. Entry dimensions are available for all variables with pathing enabled under [Traffic variables](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) in Report suite settings.

>[!TIP]
>If you want to see data based on the first hit of a visit instead of the first value seen in a visit, you can use a [segment](/help/components/segmentation/seg-overview.md). Use a hit container where [Hit depth](hit-depth.md) equals 1, then use that segment with the desired variable.

## Populate entry dimensions with data

A given entry [dimension](overview.md) is based on its associated traffic variable. If the non-entry variable has data, its associated entry dimension also contains data. No implementation changes are required for entry dimensions if your traffic variables contain data.

## Dimension items

Since entry variables are typically based on custom strings in your implementation, your organization determines what the dimension items are. Values in a given entry dimension match dimension items in its associated non-entry dimension. For example, dimension items in the 'Entry page' dimension contain similar dimension items in the 'Page' dimension.

## Entry page original

The 'Entry page original' dimension operates differently than other entry dimensions. Instead of preserving the entry page for a given visit, it preserves the very first entry page for the entire life of that visitor's cookie. For example, if you land on `https://example.com/page4` for your first visit to the site, then a year later land on `https://example.com/store`, The 'Entry page original' dimension lists `https://example.com/page4` as the dimension item.
