---
title: Site section
description: The name of the site section.
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
TQID: https://experienceleague.adobe.com/fZwN-24--98XULDEgHR-5dcIsiYXspaSOsv1t-M0iys
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
# Site section

The 'Site section' [dimension](overview.md) lists the names of site sections on your site. For large sites, it is helpful to group pages into sections. This dimension is useful to see the top-viewed or top-performing site sections.

This dimension is related to the [Page](page.md) and [Server](server.md) dimensions. Page is most granular, Server is least granular, and Site section is between the two.

## Populate this dimension with data

This dimension retrieves data from the [`ch` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the [`channel`](/help/implement/vars/page-vars/channel.md) variable.

## Dimension items

Dimension items include the names of site sections on your site. Your organization determines what specific dimension items you want to use. Whatever method you use, make sure it is consistent and that you record it in a [solution design document](/help/implement/prepare/solution-design.md).
