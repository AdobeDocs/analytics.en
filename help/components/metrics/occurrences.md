---
title: Occurrences
description: The number of hits that a variable was set or persisted.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
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