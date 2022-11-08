---
title: Hierarchy
description: A custom dimension that you can use in reporting.
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
---
# Hierarchy

>[!IMPORTANT]
>
>This dimension is retired and not an available dimension in Analysis Workspace. Adobe recommends using [eVars](evar.md) and classifications instead.

Hierarchies are custom variables that you can use however you'd like. They do not persist beyond the hit that they are set. Up to 5 hierarchies are available if your contract with Adobe supports it.

## Populate hierarchies with data

Each hierarchy collects data from the [`h1` - `h5` query string](/help/implement/validate/query-parameters.md) in image requests. For example, the `h1` query string parameter collects data for Hierarchy 1, while the `h4` query string parameter collects data for Hierarchy 4.

AppMeasurement, which compiles JavaScript variables into an image request for data collection, uses the variables `hier1` - `hier5`. See [hier](/help/implement/vars/page-vars/hier.md) in the Implement user guide for implementation guidelines.

## Dimension items

Since hierarchies contain custom strings in your implementation, your organization determines what the dimension items are for each hierarchy. Make sure that you record the purpose of each hierarchy and typical dimension items in a [solution design document](/help/implement/prepare/solution-design.md).
