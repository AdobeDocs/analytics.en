---
title: Instances
description: The number of hits that a variable was set (and not persisted).
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
---
# Instances

The 'Instances' metric shows the number of times a dimension was explicitly defined in an image request. Some dimensions, such as [eVars](../dimensions/evar.md), persist dimension items past the hit they are set on. This metric is useful when you want to see the number of times a dimension item was set without the hits where that value persisted.

## How this metric is calculated

Out of all hits in a report suite, only include hits that explicitly set a dimension item in the image request. Some dimensions, such as [eVars](../dimensions/evar.md), persist beyond the hit they are set on. Metrics like [Page views](page-views.md) and [Occurrences](occurrences.md) count both initial and persisted values. This metric does not count persisted values.

For example, a visitor arrives on your site and uses internal search. You track internal search in eVar1. After using internal search once, they visit five more pages before leaving.

If viewing a report in Workspace, you would see one eVar1 instance and six occurrences. The one instance triggered on the search results page, whereas the occurrences counted the initial value as well as the persisted values.
