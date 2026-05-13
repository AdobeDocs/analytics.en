---
title: Hierarchy
description: (Retired) A custom dimension that you can use in reporting.
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
TQID: https://experienceleague.adobe.com/7WnYvaE3qCfYGWcX6IuvMZiF0MJq50Izz6i2LNg4h6c
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
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Hierarchy

>[!IMPORTANT]
>
>This dimension is retired and not an available [dimension](overview.md) in Analysis Workspace. Adobe recommends using [eVars](evar.md) and classifications instead.

Hierarchies are custom variables that you can use however you'd like. They do not persist beyond the hit that they are set. Up to 5 hierarchies are available if your contract with Adobe supports it.

## Populate hierarchies with data

Each hierarchy collects data from the [`h1` - `h5` query string](/help/implement/validate/query-parameters.md) in image requests. For example, the `h1` query string parameter collects data for Hierarchy 1, while the `h4` query string parameter collects data for Hierarchy 4.

AppMeasurement, which compiles JavaScript variables into an image request for data collection, uses the variables `hier1` - `hier5`. See [hier](/help/implement/vars/page-vars/hier.md) in the Implement user guide for implementation guidelines.

## Dimension items

Since hierarchies contain custom strings in your implementation, your organization determines what the dimension items are for each hierarchy. Make sure that you record the purpose of each hierarchy and typical dimension items in a [solution design document](/help/implement/prepare/solution-design.md).
