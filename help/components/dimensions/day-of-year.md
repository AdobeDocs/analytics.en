---
title: Day of year
description: The numeric day of the year, regardless of which year.
feature: Dimensions
exl-id: 40a95926-3d1b-4e9c-a82a-6e23b711e6e7
TQID: https://experienceleague.adobe.com/X-Is9URgykjJAAdTlJjzqQnrHMlAnzyoC2tMFT2q9T0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
# Day of year

The 'Day of year' [dimension](overview.md) reports the numeric day of any given year as a dimension item. This report is valuable if you want a report broken out by the day of the year, but do not want a static date as dimension items.

## Populate this dimension with data

This dimension works out of the box for all implementations. If a report suite contains data, this dimension works.

## Dimension items

Dimension items include the numbers `1` (January 1) to `366` (December 31 on leap year), representing the day of the year that the hit occurred on.
