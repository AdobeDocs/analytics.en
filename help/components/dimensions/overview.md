---
title: Dimensions Overview
description: Learn what dimensions are and how they are used in Adobe Analytics.
feature: Dimensions
exl-id: dc00e06a-fdb5-40e3-82e2-269bad3b3677
TQID: https://experienceleague.adobe.com/WypIneraYlrSyIpXv3UQWIFn42A-Dxi0SxeJ2VbeubQ
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
---
# Dimensions overview

Dimensions are variables in Adobe Analytics that typically contain string values. Common dimensions include [Page](page.md), [Referring domain](referring-domain.md), or an [eVar](evar.md). In contrast, [metrics](../metrics/overview.md) contain numeric values that tie to a dimension. A basic report shows rows of string values (dimension), against a column of numeric values (metric).

For example, if you combined the **[!UICONTROL Page]** dimension with the **[!UICONTROL Visits]** metric, you would get a ranked report showing your top-visited pages:

| Page | Visits |
| --- | ---: |
| Home page | 800 |
| Product page | 500 |
| Purchase page | 100 |

{style="table-layout:fixed"}

Each dimension represents a different part or facet of your site. You can combine one of more of these dimensions with one or more metrics to create a desired report.

## Add dimension descriptions

Analytics administrators can add descriptions for dimensions and other components either within the Report Suite or directly within Analysis Workspace. For information about how to add descriptions to dimensions, see [Add component descriptions](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Retired dimensions

The following dimensions are retired. Most were Reports & Analytics reports that are not available in Analysis Workspace. They are documented here for reference if you encounter them in legacy reporting or historical data.

* **Hierarchy**: A custom dimension (`hier1`–`hier5`) used to capture a site's hierarchical structure for reporting. It is retired and not available in Analysis Workspace. Use [eVars](evar.md) and classifications instead.
* **Home Page**: A flag indicating whether the current page was the visitor's browser home page. It is a legacy dimension with no modern equivalent due to modern browser privacy practices.
* **JavaScript Support**: Indicated whether the visitor's browser supported JavaScript. A legacy dimension that is no longer meaningful for modern measurement.
* **JavaScript Version**: Reported the JavaScript version the visitor's browser supported. A legacy dimension that is no longer collected.
* **Next Page**: A pathing dimension showing the next page a visitor viewed. Use the [Flow visualization](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) in Analysis Workspace for current pathing dimensions.
* **Previous Page**: A pathing dimension showing the previous page a visitor viewed. Use the [Flow visualization](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) in Analysis Workspace for current pathing dimensions.
* **Time Zone**: The visitor's time zone, derived from the timestamp offset in AppMeasurement image requests. The Web SDK collects time zone using [`placeContext`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/context).
* **Top Level Domain**: The top-level domain of the visitor's access point. A legacy Reports & Analytics report; use the [Domain](domain.md) dimension instead.
* **Visit Page Number**: The page number within a visit. A legacy Reports & Analytics report; use the [Hit Depth](hit-depth.md) dimension instead.
* **Visitor State**: Reported the U.S. state from the `s.state` variable. It is retired in favor of the [US States](us-states.md) dimension, which uses geosegmentation.
