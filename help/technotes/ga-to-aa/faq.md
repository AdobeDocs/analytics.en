---
title: Frequently asked questions for migrating to Adobe Analytics
description: Get answers to frequently asked questions when moving from a third-party platform to Adobe.
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
---
# Frequently asked questions

**How can I migrate my historical data from my third-party platform to Adobe Analytics?**

Every Analytics platform has different ways of collecting, handling, and storing data. Rather than migrating historical data, Adobe recommends establishing a clear cut-over date to start collecting and using data within Adobe Analytics. Frequent cut-over dates used are the beginning of a fiscal year, the beginning of a calendar year, or the beginning of a calendar month. If users would like to view historical data, they can log in to the third-party platform to obtain any specific historical reporting needs.

If your organization is adamant about having historical data ported over to Adobe, contact your organization's Account Manager. An implementation consultant can work with your organization to translate a Google Analytics data export into a data source that can be ingested by Adobe data collection servers.

Adobe does not recommend porting historical data, as it is a complex process and is cost-prohibitive to your organization. Visitor identification is also impossible to seamlessly port to Adobe, as visitor information is stored in different cookies and different formats between platforms.

**I'm used to a segmentation dropdown in many of my reports. How can I recreate that in [!UICONTROL Analysis Workspace]?**

Dropdown filters are a flexible and robust feature in [!UICONTROL Analysis Workspace] that allows a segmentation dropdown. While in a workspace project:

1. Use ctrl+click (Windows) or cmd+click (Mac) on the components that you would like to include in the dropdown. You are not limited to just segments; any component can be included in a dropdown filter.
2. Drag the group of components into the workspace area labeled 'Drop a Segment Here'. Before letting go, hold Shift.

Users accessing this [!UICONTROL Workspace] project can now use this dropdown to apply segments or other components to the project. See [Panels Overview](/help/analyze/analysis-workspace/c-panels/panels.md) in the Adobe Analytics Tools guide for more information.

**I'm used to clicking on a dimension item to see a drilldown. How can I replicate that easy workflow in Analysis Workspace?**

Dimension items in [!UICONTROL Analysis Workspace] also have an easy breakdown workflow. Access it by using right-click instead of left-click. Right-click on a dimension item, click **[!UICONTROL Breakdown], then select the desired component. You can apply the same breakdown to multiple dimension items by using ctrl+click (Windows) or cmd+click (Mac) on each value.
