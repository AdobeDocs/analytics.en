---
title: Reloads
description: The number of times the page was reloaded.
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
---
# Reloads

The 'Reloads' [metric](overview.md) shows the number of times a dimension item was present during a reload. A visitor refreshing their browser is the most common way to trigger a reload.

## How this metric is calculated

This metric counts the number of hits where the [Page](../dimensions/page.md) dimension contains the same value as the previous hit.

The concept of a reload applies to the Page dimension regardless of what dimension that you use in reporting. For example, if you use [eVar1](../dimensions/evar.md) as a dimension and Reloads as a metric, the table shows you the number of times that each eVar value was present during a reload (two consecutive page values). It does not show the number of times two consecutive eVar1 values were present.
