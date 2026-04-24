---
title: Page
description: The name of the page.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
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
# Page

The 'Page' [dimension](overview.md) lists the names of pages on your site. It is one of the most common dimensions used in Adobe Analytics, as it provides insight on which pages on your site perform the best.

This dimension is related to the [Site section](site-section.md) and [Server](server.md) dimensions. Page is most granular, Server is least granular, and Site section is between the two.

## Populate this dimension with data

This dimension retrieves data from the [`pageName` query string](/help/implement/validate/query-parameters.md) in [Page view calls (`t()`)](/help/implement/vars/functions/t-method.md). [Link tracking calls (`tl()`)](/help/implement/vars/functions/tl-method.md) always strip this dimension, even if the `pageName` query string exists.

AppMeasurement collects this data using the [`pageName`](/help/implement/vars/page-vars/pagename.md) variable. If the `pageName` variable is not set, this dimension falls back to using the [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variable.

## Dimension items

Dimension items include the names of pages on your site. Your organization determines what specific dimension items that you want to use. Some organizations directly use `document.title`, while others formulate a custom breadcrumb. Whatever method you use, make sure it is consistent and that you record it in a [solution design document](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Analysis Workspace uses last attribution by default, with the option to use any attribution model.
