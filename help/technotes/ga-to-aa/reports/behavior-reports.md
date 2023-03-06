---
title: Behavior reports in Adobe Analytics
description: Learn how to create behavior reports in Adobe Analytics
feature: Third-party Integration
exl-id: ea441afa-e595-4ffa-b446-d67e87f8a7c9
---
# Behavior reports

Behavior reports show information on how users interact with your site.

This page assumes the user has a basic knowledge of using Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Behavior flow

The behavior flow report can be recreated using the Flow visualization.

1. Click the visualizations icon on the left, and drag a Flow visualization onto the workspace above the freeform table
2. Locate the **Page** dimension, then click the Arrow icon to reveal page values. Dimension items are colored yellow.
3. Locate the desired page value to start with, and drag it into the space labeled 'Dimension or item' in the center
4. This flow report is interactive. Click any of the values to expand the flows to subsequent or previous pages. Use the right-click menu to expand or collapse columns. Different dimensions can also be used within the same flow report.

![Flow Report](/help/technotes/ga-to-aa/assets/flow.png)

## Site Content - All Pages

The pages report shows the performance of individual pages on your site.

1. In the Components menu, locate the **Pages** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

As an alternative, Adobe provides several pre-created workspaces called templates. The Content Consumption (Web) template provides similar value to the all pages report.

1. Click *[!UICONTROL Project] > [!UICONTROL New]*, which opens a modal window with project options.
2. Click the Content Consumption (Web) template, then click Create.

## Site Content - Content Drilldown

The content drilldown report lets you take a look at page traffic by URL structure. Additional implementation is required for use in Analysis Workspace. Adobe recommends working with an implementation consultant to ensure this data is accurately collected.

## Site Content - Landing Pages

The landing pages report shows the top landing pages on your site. Landing pages are available in Analysis Workspace as the **Entry Page** dimension.

1. In the Components menu, locate the **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Adobe recommends using the **Visits** metric for this dimension.

## Site Content - Exit Pages

The exit pages report shows the top pages that became the last page of an individual's visit. It is available in Analysis Workspace under the same name.

1. In the Components menu, locate the **Exit Page** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Adobe recommends using the **Visits** metric for this dimension.

## Site Speed reports

Site speed reports show how quickly pages load, revealing opportunities to increase your page load times.

This feature requires additional implementation on both platforms; Adobe recommends working with an implementation consultant to ensure this data is correctly configured for Analysis Workspace. The [getPageLoadTime plug-in](/help/implement/vars/plugins/getpageloadtime.md) is typically assigned to an eVar to obtain performance data in Adobe Analytics.

## Site Search reports

Site search reports provide insight on how visitors use your site's internal search capabilities.

This feature requires additional implementation on both platforms; Adobe recommends working with an implementation consultant to ensure this data is correctly configured for Analysis Workspace. Typically an internal search term is pulled from a query string parameter and placed into an eVar for reporting.

## Events reports

Events have some major structural differences between Google and Adobe Analytics. Both require additional implementation changes to work properly on their respective platform.

* In Google Analytics, events are defined in your implementation as text. Events have categories, actions, and labels.
* In Adobe Analytics, events are first set up in the Admin Console where it is assigned an identifier. That identifier is used in implementation code. For example:
    1. You could set event1 in the Admin Console as 'Registrations'.
    2. In your implementation, you would include event1 in the events variable on the registration confirmation page. Every time the registration confirmation page is displayed, event1 increases.
    3. In Analysis Workspace, 'Registrations' appears as a metric for use in any report.

Because this feature requires implementation changes, Adobe recommends working with an implementation consultant to ensure data is correctly configured for Analysis Workspace.

## Publisher reports

Similar to how Google requires a connection with Google Ad Manager, Adobe offers a dedicated product to provide insight called Adobe Advertising Cloud. If your organization is interested in using this product, contact your organization's Account Manager.
