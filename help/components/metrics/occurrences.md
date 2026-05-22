---
title: Occurrences
description: The number of hits that a variable was set or persisted.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
TQID: https://experienceleague.adobe.com/04bDCj1dkVb9gIDMbpvvGea92oOzd-N0XLfzf4t-6iA
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
# Occurrences

The 'Occurrences' [metric](overview.md) shows the number of hits where a given dimension was set or persisted. When you drag a dimension in Workspace to a blank canvas, Adobe automatically applies this metric to the project.

## How this metric is calculated

Out of all hits in a report suite, include hits where a dimension item is defined or persisted. Some dimensions, such as [eVars](../dimensions/evar.md), persist beyond the hit they are set on. This metric counts both initial and persisted values.

## Compare to similar metrics

* **Occurrences vs. [Instances](instances.md)**: Occurrences count hits where a dimension item was set or persisted. Instances do not include hits where a dimension item persists.
* **Occurrences vs. [Page views](page-views.md)**: Occurrences include all hit types, including page view tracking calls ([`t()`](/help/implement/vars/functions/t-method.md)), link tracking calls ([`tl()`](/help/implement/vars/functions/tl-method.md)), and data from summary [Data sources](/help/import/data-sources/overview.md). The page views metric only includes page view tracking calls, excluding link tracking calls and summary data sources.

## Persistence

Persistence is the ability for a given dimension value to relate to a metric beyond the event it is set on. It uses a combination of allocation and expiration. Allocation lets you determine which value is kept when more than one dimension item can persist at a time in a single column. Expiration lets you determine how long a dimension item persists beyond the event it is set on.

Persistence is available only on dimensions, and is retroactive to the data it is applied to. It is an immediate data transformation that happens before filtering or other analysis operations are applied. If persistence is not enabled, the dimension only relates to metrics that exist in the same event.
