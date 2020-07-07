---
description: Rollup report suites aggregate data from multiple child report suites and display them in a summarized data set.
title: Rollup and global report suites
topic: Admin tools
uuid: c90b8e38-2c95-4318-8165-a362106b6142
---

# Rollup and global report suites

Rollup report suites aggregate data from multiple child report suites and display them in a summarized data set. They provide a convenient place to see summed totals such as page views, revenue, or other basic dimensions. Rollups are frequently used because they do not require additional implementation.

## Definitions of Report Suite Types

**Global report suite**: Implementation is altered to send image requests across domains into a single global report suite. If hits are also sent to individual report suites, this practice is known as multi-suite tagging.

**Rollup report suite**: Created in Admin Tools. Takes the sum of each metric at the end of every day.

* Rollups are free to use and do not increase server call usage.
* Rollups provide total data, but do not report individual values in reports. For example, eVar1 values are not included, but its aggregate total can be.
* Data is not deduplicated when combining data across report suites.
* Rollups run on a nightly basis.
* When adding a report suite to an existing rollup, historical data is not included in the rollup.
* All child report suites must have data in them in order for a rollup to function. If new report suites are included in a rollup, make sure to send at least one page view to those report suites.
* Rollup report suites are limited to a maximum of 40 child report suites.
* Rollup report suites are limited to a maximum of 100 events.
* Data contained in Rollup report suites does not support breakdowns or segments.
* The Pages report is replaced with the Most Popular Sites report, which reports on metrics at the child-suite level.

## Rollup vs. Global Report Suites

**Secondary server calls**: Rollups do not incur any additional server calls beyond what a single report suite collects. If your organization uses multi-suite tagging, secondary server calls are made for each additional report suite included in an image request.

>[!TIP]
>
>If you use only a global report suite with [virtual report suites](../../components/vrs/vrs-considerations.md), no secondary server calls are needed.

**Implementation changes**: Rollups do not require any implementation changes, while global report suites require you to include the global report suite ID in your implementation.

**Duplication**: Global report suites deduplicate unique visitors, while rollups do not. For example, if a user visits three of your domains in the same day, rollups would count three daily unique visitors. Global report suites would record one unique visitor.

**Time frame**: Rollups are only processed at midnight each night, while global report suites report data with standard latency.

**Breadth**: Rollups have no way to communicate between report suites. Global report suites can attribute credit to conversion variables between report suites, as well as provide pathing across report suites.

**Historical data**: Rollups can aggregate historical data, while global report suites only report data from the point they were implemented.

**Reports**: Global report suites provide data on all dimensions; rollups provide aggregate data on only high-level reports.

**Supported products**: Rollups can only be used in Reports & Analytics. They are not supported in Analysis Workspace, Data Warehouse, or Ad Hoc Analysis. Global report suites can be used across all products.

**Number of aggregated report suites**: Rollups only support a maximum of 40 child report suites. Global report suites can be implemented on any number of domains or apps that you own.
