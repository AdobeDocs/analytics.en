---
title: Instances
description: The number of hits that a variable was set (and not persisted).
---

# Instances

The 'Instances' metric shows the number of times a dimension was explicitly defined in an image request. Some dimensions, such as [eVars](../dimensions/evar.md), persist dimension values past the hit they are set on. This metric is useful when you want to see the number of times a dimension value was set without the hits where that value persisted.

## How this metric is calculated

Out of all hits in a report suite, only include hits that explicitly set a dimension value in the image request. Some dimensions, such as [eVars](../dimensions/evar.md), persist beyond the hit they are set on. Metrics like [Page views](page-views.md) and [Occurrences](occurrences.md) count both initial and persisted values. This metric does not count persisted values.