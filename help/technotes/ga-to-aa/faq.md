---
title: Frequently Asked Questions for migrating to Adobe Analytics
description: Get answers to frequently asked questions when moving from a third-party platform to Adobe.
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
TQID: https://experienceleague.adobe.com/NJPnGHUG-9krAfzRZiNbMd7DS9q5gRGTm-1KM3DMXag
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
    internal-label: Panels
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Frequently Asked Questions for migrating to Adobe Analytics

**How can I migrate my historical data from my third-party platform to Adobe Analytics?**

Every Analytics platform has different ways of collecting, handling, and storing data. Rather than migrating historical data, Adobe recommends establishing a clear cut-over date to start collecting and using data within Adobe Analytics. Frequent cut-over dates used are the beginning of a fiscal year, the beginning of a calendar year, or the beginning of a calendar month. If users would like to view historical data, they can log in to the third-party platform to obtain any specific historical reporting needs.

If your organization is adamant about having historical data ported over to Adobe, contact your Adobe Account Team. An implementation consultant can work with your organization to translate a Google Analytics data export into a data source that can be ingested by Adobe data collection servers.

For moving over historical data the recommendation is to use [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-overview) which can bring in any omni-channel data source.

**I'm used to a segmentation drop-down list in many of my reports. How can I recreate that in [!UICONTROL Analysis Workspace]?**

Drop-down filters are a flexible and robust feature in [!UICONTROL Analysis Workspace] that allows a segmentation drop-down list. While in a workspace project:

1. Use ***ctrl***+***click*** (Windows) or ***cmd***+***click*** (Mac) on the components that you would like to include in the drop-down filter. You are not limited to just segments. Any component can be included in a drop-down filter.
2. Drag the group of components into the workspace area labeled *Drop a Segment Here*. Before letting go, hold **[!UICONTROL shift]**.

Users accessing this [!UICONTROL Workspace] project can now use this drop-down filter to apply segments or other components to the project. See [Panels Overview](/help/analyze/analysis-workspace/c-panels/panels.md) in the Adobe Analytics Tools guide for more information.

**I'm used to clicking on a dimension item to see a drilldown. How can I replicate that easy workflow in Analysis Workspace?**

Dimension items in [!UICONTROL Analysis Workspace] also have an easy breakdown workflow. Access the breakdown by using the context menu on a dimension item. Then select **[!UICONTROL Breakdown]**, and the desired component. You can apply the same breakdown to multiple dimension items by using ***ctrl***+***select*** (Windows) or ***cmd***+***select*** (Mac) on each value.
