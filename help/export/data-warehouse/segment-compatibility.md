---
title: Data Warehouse segment compatibility
description: Learn what segment definitions are valid for use in Data Warehouse.
feature: Data Warehouse
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
    internal-label: Segment Builder
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
---
# Data Warehouse segment compatibility

Not all segments built in the segment builder can be used in Data Warehouse. Use this page to learn what segment definitions are compatible with Data Warehouse so that it is available to select when you [create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md).

A segment is compatible with Data Warehouse only when **both** of the following are true:

* **Supported components**: The segment uses only dimensions and metrics that Data Warehouse supports.
* **Supported structure**: The segment's structure follows the rules that Data Warehouse enforces.

If either condition is not met, the segment does not appear as an option when you build a Data Warehouse request, and an error displays if you select a virtual report suite that contains an incompatible segment.

## Supported components

Because a segment is evaluated against the same data as the request it is applied to, **any component that is not supported in a Data Warehouse request is also unsupported in a segment.** For the full list of dimensions and metrics that Data Warehouse does not support, see [Component support in Data Warehouse](component-support.md).

In addition to the dimension and metrics listed in [Component support](component-support.md), the following dimensions are available in a Data Warehouse *request* but **cannot be used inside a segment definition**:

* [[!UICONTROL Day of Month]](/help/components/dimensions/day-of-month.md)
* [[!UICONTROL Day of Week]](/help/components/dimensions/day-of-week.md)
* [[!UICONTROL Day of Year]](/help/components/dimensions/day-of-year.md)
* [[!UICONTROL Hour of Day]](/help/components/dimensions/hour-of-day.md)
* [[!UICONTROL Marketing Channels]](/help/components/dimensions/marketing-channel.md) (use [[!UICONTROL Last touch channel]](/help/components/dimensions/last-touch-channel.md) instead)
* [[!UICONTROL Month of Year]](/help/components/dimensions/month-of-year.md)
* [[!UICONTROL Pages Not Found]](/help/components/dimensions/pages-not-found.md) (use [[!UICONTROL Page type error]](/help/components/dimensions/pages-not-found.md) instead)
* [[!UICONTROL Quarter of Year]](/help/components/dimensions/quarter-of-year.md)
* [[!UICONTROL Weekday/Weekend]](/help/components/dimensions/weekday-weekend.md)

## Supported structure

Even when a segment uses only supported components, its structure must follow the rules that Data Warehouse enforces. Segment structures are fully supported, partially supported, or unsupported:

**Supported**:

* **Segment stacking**: Multiple segments can be applied to a single Data Warehouse request.
* **Nested containers**: Supported, provided scope decreases at each level (visitor &rarr; visit &rarr; hit). Containers that increase in scope are not supported.

**Partially supported**:

* **Exclude containers**: Supported only at the top level. Data Warehouse supports only segments expressible as `A AND NOT B` — that is, **include this characteristic** and **exclude this characteristic**. Exclude containers nested within other containers are not supported.
* **AND/OR logic**: Supported with limitations. When using an `exclusion` or `without` container in combination with AND/OR logic, only segments that can be rewritten as `A AND NOT B` are supported.

**Unsupported**:

* **Sequential segments**: Segments using the THEN operator to define ordered visitor navigation sequences are not supported.
* **"Equals any of" and "Does not equal any of" operators**: These operators are not supported in Data Warehouse segments.

## Segments used as dimensions

When you use a segment as a dimension in a Data Warehouse report, the report returns a column containing `"0"` or `"1"`:

* **`"0"`**: The dimension item did not meet the segment's criteria.
* **`"1"`**: The dimension item met the segment's criteria.
