---
title: Audience reports in Adobe Analytics
description: Learn how to create audience-based reports using Analysis Workspace.
feature: Third-party Integration
exl-id: 739b0c3d-3f74-41fa-a2cc-f02c17d85ce2
---
# Audience reports

Audience reports show information about the types of people that visit your site.

This page assumes the user has a basic knowledge of using Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Active Users

Active users show the cumulative number of users to your site in the prior 1, 7, 14, or 28 days. While Adobe does not have the exact calculation used in Google Analytics, you can use the metric Unique Visitors to see a deduplicated count of users to your site based on the selected date range.

To obtain a line graph of unique visitors:

1. Click the Visualizations icon on the left, and drag the Line visualization onto the workspace above the empty freeform table.
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the smaller space labeled 'Drop a Metric here'.
3. If different granularity is desired, drag the desired date range (e.g. **Day**, **Week**, **Month**, etc.) on top of the existing date dimension header.

See [Unique Visitors](/help/components/metrics/unique-visitors.md) in the Components user guide for details on how Adobe calculates unique visitors.

## Lifetime Value

Lifetime value is a feature that requires additional specialized implementation on both platforms. Adobe recommends working with an implementation consultant to obtain this data.

## Cohort Analysis

Cohort Analysis shows how often the same users return to your site.

To create a cohort table:

1. Click the Visualization icon on the left, and drag the Cohort Table visualization onto the workspace.
2. Click the Components icon on the left, then drag the **Visits** metric onto both the Inclusion Criteria and Return Criteria.
3. Click Build.

See [Cohort Analysis](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) in the Analysis Workspace user guide for details on additional customizations to the cohort visualization.

## Audiences

The Audiences report in Google Analytics requires the setting up of audiences. Audiences also require configuration in Adobe through Adobe Audience Manager. See the Adobe Audience Manager user guide for more information.

## User Explorer

The User Explorer report allows an analyst to view individual visits through anonymized identifiers. Adobe does not surface the backend identifiers outside of data feeds, which are hit-level raw exports of data.

* If this data is desired in Analysis Workspace, it is possible to work with an implementation consultant to pass the anonymized unique identifier cookie value into an eVar. Note that this only works with smaller implementations consisting of less than 1 million unique visitors per month.
* If this data is desired within data feeds, the concatenated columns `visid_high` and `visid_low` are the most common way to identify unique visitors. Learn more about [Data Feeds](/help/export/analytics-data-feed/data-feed-overview.md) in the Export user guide.

## Demographics and Interests reports

Demographics and interests data provides information about the age, gender, and interests of site users. That data is collected by Google through their cross-site tracking abilities.

Demographic and interests data is not automatically collected by Adobe. However if your organization obtains this data, you can use Customer Attributes, a feature within the Adobe Experience Cloud Platform. It allows full control over the organizing of data by attributes, and is not limited to just demographics or interests.

See Customer Attributes Help for more information.

## Geo - Language

The geo language report shows site traffic by the language setting in the visitor's browser.

To create a language report:

1. In the Components menu, locate the **Language** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Language](/help/components/dimensions/language.md) dimension in the Components user guide for more information.

## Geo - Location

The geo location report gives a worldwide map view, breaking data out by country.

To create a geo location report:

1. Click the Visualizations icon on the left, and drag the Map visualization onto the workspace above the empty freeform table.
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the space labeled 'Add Metric'.
3. Click Build.

If the table is also wanted in addition to the map:

1. In the Components menu, locate the **Countries** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Countries](/help/components/dimensions/countries.md) dimensions in the Components user guide for more information.

## Behavior - New vs Returning

The new vs returning report gives a simplified view of first sessions (new visits) vs. subsequent sessions (return visits).

To create a new vs returning visits report:

1. In the components menu, locate the **First Time Visits** segment and drag it onto the large freeform table area labeled 'Drop a Dimension here'. Note that **First Time Visits** is a segment, while Workspace typically uses dimensions to represent rows.
2. Locate the **Return Visits** segment and drag it on top of the Segments row header. This adds the segment as a dimension below First Time Visits, allowing an easy comparison.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

If a line graph is also wanted:

1. Click the visualizations icon on the left, and drag a Line visualization onto the workspace above the freeform table
2. Use ctrl+click (Windows) or cmd+click (Mac) on each row in the freeform table to highlight them. This allows both trends to appear in the line visualization.
3. Click the small round colored dot in the upper left corner of the line visualization, then click the checkbox 'Lock Selection'.

## Behavior - Frequency & Recency

The frequency & recency report is approximately equal to the **Visit Number** dimension in Analysis Workspace.

1. In the components menu, locate the **Visit Number** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Visit Number](/help/components/dimensions/visit-number.md) dimension in the Components user guide for more information.

## Behavior - Engagement

The engagement report is approximately equal to the **Time Spent per Visit - Bucketed** dimension.

1. In the components menu, locate the **Time Spent per Visit - Bucketed** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Time Spent per Visit](/help/components/dimensions/time-spent-per-visit.md) dimension in the Components user guide for more information.

## Technology - Browser & OS

There are multiple primary dimensions available in the Browser & OS report.

* The **Browser** primary dimension is also available in Analysis Workspace as a dimension.
* The **Operating System** primary dimension is also available in Analysis Workspace as a dimension.
* The **Screen Resolution** primary dimension is available in Analysis Workspace as the **Monitor Resolution** dimension.
* The **Screen Colors** primary dimension is available in Analysis Workspace as the **Color Depth** dimension.
* The **Flash Version** primary dimension is not available in Adobe Analytics, however this data can be collected by an eVar if wanted.

1. In the components menu, locate the desired dimension noted above and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the following pages in the Components user guide for more information on their respective dimension:

* [Browser](/help/components/dimensions/browser.md)
* [Operating System](/help/components/dimensions/operating-systems.md)
* [Monitor Resolution](/help/components/dimensions/monitor-resolution.md)
* [Color Depth](/help/components/dimensions/color-depth.md)

## Technology - Network

The network report is approximately equal to the **Domain** dimension.

1. In the components menu, locate the **Domain** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Domain](/help/components/dimensions/domain.md) dimension in the Components user guide for more information.

## Mobile - Overview

The mobile overview report is approximately equal to the **Mobile Device Type** dimension. Note that the 'Other' value is equivalent to desktop traffic.

1. In the components menu, locate the **Mobile Device Type** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile device type](/help/components/dimensions/mobile-dimensions.md) dimension in the Components user guide for more information.

## Mobile - Devices

The mobile devices report is approximately equal to the **Mobile Device** dimension.

1. In the components menu, locate the **Mobile Device** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile device](/help/components/dimensions/mobile-dimensions.md) dimension in the Components user guide for more information.

## Custom

Custom reports are defined on a per-implementation basis. Work with your organization's Analytics administrator and/or implementation consultant to interpret these reports. Typically an organization maintains a [Solution Design Document](/help/implement/prepare/solution-design.md) to keep track of custom variable values and how they are populated.

## Benchmarking

Benchmarking reports allow you to see how facets of your data compare to industry averages. Adobe does not share benchmarking data between its customers at this time.

## Users Flow

The flow report is available on both platforms. To create a flow report:

1. Click the visualizations icon on the left, and drag a Flow visualization onto the workspace above the freeform table
2. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. Dimension items are colored yellow.
3. Locate the desired page value to start with, and drag it into the space labeled 'Dimension or item' in the center
4. This flow report is interactive. Click any of the values to expand the flows to subsequent or previous pages. Use the right-click menu to expand or collapse columns. Different dimensions can also be used within the same flow report.
