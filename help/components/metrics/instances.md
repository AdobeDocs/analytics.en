---
title: Instances
description: The number of hits that a variable was set (and not persisted).
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
TQID: https://experienceleague.adobe.com/a6Ycw6CVzeSKuOCHezQtLNIZZo6vbkVneVWO0C2QfxQ
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
# Instances

The 'Instances' [metric](overview.md) shows the number of times a dimension was explicitly defined in an image request. Some dimensions, such as [eVars](../dimensions/evar.md), persist dimension items past the hit they are set on. This metric is useful when you want to see the number of times a dimension item was set without the hits where that value persisted.

## How this metric is calculated

Out of all hits in a report suite, only include hits that explicitly set a dimension item in the image request. Some dimensions, such as [eVars](../dimensions/evar.md), persist beyond the hit they are set on. Metrics like [Page views](page-views.md) and [Occurrences](occurrences.md) count both initial and persisted values. This metric does not count persisted values.

For example, a visitor arrives on your site and uses internal search. You track internal search in eVar1. After using internal search once, they visit five more pages before leaving.

If viewing a report in Workspace, you would see one eVar1 instance and six occurrences. One instance counts on the search results page, whereas the occurrences metric counts the initial value and subsequent persisted values.

## Compare to similar metrics

* **Instances vs. [Occurrences](occurrences.md)**: Instances do not include hits where a dimension item persists. Occurrences count hits where a dimension item was set or persisted.
* **Instances vs. [Page views](page-views.md)**: Instances include all hit types, including page view tracking calls ([`t()`](/help/implement/vars/functions/t-method.md)), link tracking calls ([`tl()`](/help/implement/vars/functions/tl-method.md)), and data from summary [Data sources](/help/import/data-sources/overview.md). The page views metric only includes page view tracking calls, excluding link tracking calls and summary data sources.
