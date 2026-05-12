---
title: Server
description: The name of the server.
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
TQID: https://experienceleague.adobe.com/BDVwwy3jCtHrcWLy2nOHVnDRbFiAoR-EeOzp-35XjBs
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
# Server

The 'Server' [dimension](overview.md) typically lists the hostname of the site. For report suites that combine multiple domains or subdomains, this dimension is valuable to see which domains or subdomains perform the best.

This dimension is related to the [Page](page.md) and [Site section](site-section.md) dimensions. Page is most granular, Server is least granular, and Site section is between the two.

## Populate this dimension with data

This dimension retrieves data from the [`server` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the [`server`](/help/implement/vars/page-vars/server.md) variable.

## Dimension items

Dimension items include servers on your site. Your organization determines what specific dimension items you want to use. Some organizations use `window.location.hostname`, while others formulate a custom values. Whatever method you use, make sure it is consistent and that you record it in a [solution design document](/help/implement/prepare/solution-design.md).
