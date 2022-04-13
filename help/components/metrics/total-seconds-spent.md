---
title: Total seconds spent
description: The aggregated total number of seconds spent on the dimension item.
feature: Metrics
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
---
# Total seconds spent

The 'Total seconds spent' metric shows the aggregated number of seconds a visitor spent on a given dimension item. This metric is useful when you want the raw amount of time spent on a given dimension item, and not averages like other time spent metrics offer.

In Report Builder, this metric is named 'Total time spent'.

## How this metric is calculated

This metric uses the following steps to measure calculation:

1. For a given hit, look at the timestamp.
2. Compare this hit with the timestamp of the next hit in the visit. Both page view and link tracking hits count.
3. The amount of seconds that elapsed between the two hits contribute towards the dimension item.

Persisted variables, such as [eVars](../dimensions/evar.md), count towards total seconds spent. Traffic variables, such as [props](../dimensions/prop.md), include seconds spent across subsequent link tracking calls.

>[!TIP]
>
>Time spent is not measured for the last hit of the visit since there is not subsequent image request to measure elapsed time. This concept also applies to visits consisting of a single hit (a bounce).

See [Time spent overview](time-spent.md) for more general information on time spent.
