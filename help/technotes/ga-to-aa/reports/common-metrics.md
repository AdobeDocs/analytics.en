---
title: Commonly used metrics on other platforms translation guide
description: Understand how to pull metric data for many common reports using terminology more familiar to Google Analytics users.
---

# Commonly used metrics on other platforms translation guide

On other platforms such as Google Analytics, many reports share a common number of metrics. Use this page to understand how to recreate the metrics used in many reports.

To add multiple metrics to a workspace freeform table, drag the metric from the components area next to the metric header in the workspace:

![Additional metric](../assets/new_metric.png)

## Acquisition metrics

**Users** is approximately equal to `Unique Visitors` in Workspace. See the [Unique Visitors](../../../components/c-variables/c-metrics/metrics-unique-visitors.md) metric in the Components user guide for additional details.

**New Users** can be obtained by the following:

1. Drag the `Unique Visitors` metric onto the workspace.
2. Drag the `First Time Visits` segment above the Unique Visitors metric headers:

    ![First Time Visits](../assets/first_time_visits.png)

**Sessions** is approximately equal to `Visits` in Analysis Workspace. See the [Visits](../../../components/c-variables/c-metrics/metrics-visit.md) metric in the Components user guide for additional details.

## Behavior metrics

**Bounce Rate** is readily available in Analysis Workspace as a metric. See the [Bounce Rate](../../../components/c-variables/c-metrics/metrics-bounce-rate.md) metric in the Components user guide for additional information.

**Pages/Session** is a calculated metric. It can be obtained by the following:

1. If you have already created this calculated metric, locate it under Metrics and drag it onto the workspace.
2. If you have not yet created this calculated metric, click the `+` icon near the metric list to open the Calculated Metric Builder.
3. Give it a title of 'Page views per visit', and a description if desired.
4. Set the format to Decimal, and set the number of decimal places to 2.
5. Drag the `Page views` metric and `Visits` metric into the definition area.
6. Arrange the definition so the formula is `Page Views divided by Visits`.
7. Click Save to go back to your workspace.
8. Drag the newly defined calculated metric onto the workspace.

    Learn more about [Calculated Metrics](../../../components/c-variables/c-metrics/calculated-metric.md) in the Components user guide.

**Avg. Session Duration** is approximately equal to `Time Spent per Visit (seconds)`. Learn more about [Time Spent](../../../components/c-variables/c-metrics/metrics-time-spent.md) metrics in the Components user guide.

## Conversions metrics

**Goal Conversion Rate**, **Goal Completions**, and **Goal Value** require additional implementation on both platforms. Adobe recommends working with an implementation consultant to obtain this data in reporting.