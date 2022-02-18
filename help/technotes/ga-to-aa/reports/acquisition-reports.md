---
title: Acquisition reports in Adobe Analytics
description: Learn how to create acquisition-based reports using Analysis Workspace.
feature: Third-party Integration
exl-id: 2929d34b-8eb0-4105-a49c-02d536929fe0
---
# Acquisition reports

Acquisition reports show how you obtain visitors to your site.

In Adobe Analytics, these reports are known as **Marketing Channels**. They require some basic initial setup, but allow a much more customized view of channels.

>[!IMPORTANT]
>
> Set up your Marketing Channel processing rules to use these reports. See [Getting Started with Marketing Channels](/help/components/c-marketing-channels/c-getting-started-mchannel.md) for information on how to best configure Marketing Channels in your organization.

This page assumes the user has a basic knowledge of using Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## All Traffic - Channels

Shows an aggregate view of all channels visitors use to reach your site.

1. In the Components menu, locate the **Marketing Channel** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## All Traffic - Treemaps

Shows a treemap of channel traffic. This report is similar to All Traffic - Channels, but is shown in a different way.

1. Click the Visualizations icon on the left, and drag the Treemap visualization onto the workspace above the empty freeform table.
2. Click the Components icon on the left, then drag the **Marketing Channel** dimension onto the large freeform table area labeled 'Drop a dimension here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.
4. Note that additional metrics create additional treemaps. If only one treemap is desired:
   1. Click the top cell of the desired metric to represent the treemap.
   2. Shift+click the last cell of that same metric column to highlight the column blue. If done correctly, one treemap is present in the visualization.
   3. Click the colored dot in the upper right corner of the treemap visualization, then click the checkbox 'Lock Selection'.

Treemaps can be applied to any dimension, not just Marketing Channels.

## All Traffic - Source/Medium

Source and medium reports show the domains that drove traffic to your site.

* The **Source** primary dimension is available in Analysis Workspace as the **Referring Domain** dimension.
* The **Medium** primary dimension is available in Analysis Workspace as the  **Referrer Type** dimension.
* The **Keyword** primary dimension is available in Analysis Workspace as the **Search Keyword** dimension.

1. In the components menu, locate the desired dimension noted above and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the following pages in the Components user guide for more information on their respective dimension:

* [Referring Domain](/help/components/dimensions/referring-domain.md)
* [Referrer Type](/help/components/dimensions/referrer-type.md)
* [Search Keyword](/help/components/dimensions/search-keyword.md)

## All Traffic - Referrals

* The **Source** primary dimension is available in Analysis Workspace as the **Referring Domain** dimension.
* The **Landing Page** primary dimension is available in Analysis Workspace as the **Entry Page** dimension.

1. In the components menu, locate the **Referring Domain** or **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Referring Domain](/help/components/dimensions/referring-domain.md) dimension in the Components user guide for more information.

## Google Ads reports and Search Console reports

Adobe uses a feature in Analysis Workspace called Advertising Analytics to bring in advertising and search data from multiple platforms, including Google.

The advertising analytics feature requires configuration to return data. See [Advertising Analytics Help](/help/integrate/c-advertising-analytics/overview.md) for details on how to enable these additional dimensions in Analysis Workspace.

## Social reports

Social reports provide similar information as their respective Behavior report, except in the context of social networks. This data is available in Analysis Workspace by combining a dimension with a segment.

Sometimes visitors reach your site through multiple channels in the same session. For example, a visitor clicks a social media page, then a few minutes later visits a search engine to reach your site. In these cases, non-social domains can appear in this report. If you would like to exclude non-social domains, sort the report by visits, or create a copy of the segment to be based on hits instead of visits. See [Segmentation Containers](/help/components/segmentation/seg-overview.md) in the Components user guide for more information.

### Social - Network Referrals

The Network Referrals report shows which social network domains drove traffic to your site. This data is available in Analysis Workspace using the **Referring Domain** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Referring Domain** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled 'Drop a segment here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social - Landing Pages

The Landing Pages report shows which pages visitors arrived on after clicking a link through a social network. This data is available in Analysis Workspace using the **Entry Page** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled 'Drop a segment here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social - Conversions

The Conversions report shows ecommerce data in context of social networks. Additional implementation is required to use these reports on both platforms; Adobe recommends working with an implementation consultant to ensure this data is correctly configured for Analysis Workspace.

### Social - Plugins

The Plugins report shows how visitors interact with embedded social media plug-ins on your site. Additional implementation is required for use in Analysis Workspace. Adobe recommends working with an implementation consultant to ensure this data is accurately collected.

### Social - Users Flow

The Users flow report shows pathing data in context of visitors arriving through a social network.

1. Click the visualizations icon on the left, and drag a Flow visualization onto the workspace above the freeform table
2. Click the Components icon on the left, then drag the **Visits from Social Sites** segment onto the small area just above the flow visualization labeled 'Drop a Segment here'.
3. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. Dimension items are colored yellow.
4. Locate the desired page value to start with, and drag it into the space labeled 'Dimension or item' in the center
5. This flow report is interactive. Click any of the values to expand the flows to subsequent or previous pages. Use the right-click menu to expand or collapse columns. Different dimensions can also be used within the same flow report.

## Campaigns - All

The campaigns report is available in Analysis Workspace using the **Tracking Code** dimension. Note that using the Tracking Code dimension requires additional implementation to collect data.

It is possible to collect UTM parameters in Adobe Analytics using custom variables (eVars). Adobe recommends working with an implementation consultant to ensure tracking code values are collected accurately in Adobe Analytics.

1. In the Components menu, locate the **Tracking Code** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Campaigns - Paid Keywords

The paid keywords report shows how each keyword performs after a visitor clicks a paid search link from a search engine. The **Search Keywords - Paid** dimension is available in Analysis Workspace, but requires a one-time setup of paid search detection to collect data. See [Paid Search Detection](/help/admin/admin/paid-search-detection/paid-search-detection.md) in the Admin user guide for setup details.

1. In the Components menu, locate the **Search Keyword - Paid** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Campaigns - Organic Keywords

The organic keywords report shows how each keyword performs after a visitor clicks an organic search link from a search engine. The **Search Keywords - Natural** dimension is available in Analysis Workspace. Note that if paid search detection is not set up, this dimension collects both paid and natural keywords.

1. In the Components menu, locate the **Search Keyword - Natural** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Cost Analysis

This report shows visit, cost, and revenue performance data for your paid marketing channels. Adobe provides a dedicated product to provide insight called Adobe Advertising Cloud. If your organization is interested in using this product, contact your organization's Account Manager.
