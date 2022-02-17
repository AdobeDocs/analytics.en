---
title: Single page visits
description: The number of times that the 'Page' dimension item did not change in a visit.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
---
# Single page visits

*This help page describes how 'Single page visits' works as a metric. See the [Single page visits](../dimensions/single-page-visits.md) dimension for more information.*

The [!UICONTROL Single page visits] metric shows the number of visits where the [Page](../dimensions/page.md) dimension item contained only a single unique value for the entire visit. This metric is helpful in the context of dimensions where you want to see short visits, but not have as stringent of a rule as [[!UICONTROL Bounces]](bounces.md) does.

## How this metric is calculated

This metric counts the number of visits where the [!UICONTROL Page] dimension item contained only a single unique value for the entire visit. If a visitor reloads the page or fires link tracking calls, it still counts as a single page visit. As soon as the Page dimension changes to a second unique value, the visit no longer qualifies as a single page visit.

See [Single access](single-access.md) for a comparison between metrics.

## Count repeat instances

This setting specifies whether repeat instances are counted in reports. For more information see [Count repeat instances](/help/components/metrics/count-repeat-instances.md). 