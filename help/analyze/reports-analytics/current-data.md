---
description: The Include Current Data option in Reports & Analytics lets you view the latest Analytics data, often before data is fully processed and finalized. Current data displays most metrics within minutes, providing actionable data for quick decision making.
subtopic: Current Data
title: Current Data
uuid: 601d3695-be13-4b7f-9df0-de01c8bd64ee
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 4e90f5ad-ba12-4282-a0d9-55765d88104b
---
# Current Data

{{ra-eol}}

The Include Current Data option in Reports & Analytics lets you view the latest Analytics data, often before data is fully processed and finalized. Current data displays most metrics within minutes, providing actionable data for quick decision making.

It is visible as an option as part of a report's settings:

![Current Data screenshot](assets/current_data.png)

Current Data is enabled by default on all reports that support it. If you would rather view all metrics after the data is fully processed, there are several options:

* Use Analysis Workspace, which uses fully processed data.
* Click 'No' in the current data report setting to only use fully processed data.
* Remove the 'Current Data' permission item from a product profile in the Admin Console to prevent non-admin users from seeing this option. See [Product profile permissions for Analytics Tools](/help/admin/admin-console/permissions/analytics-tools.md) in the Admin user guide for more information.

Due to prioritizing data availability, current data currently cannot be used with segments, classifications, breakdowns, pathing, and some metrics. If one of these features are used, current data is forced to 'No' in the report and a yellow notice is shown explaining why current data is not available.

![Current data notice](assets/current_data_notice.png)

## Typical Current Data Latency

Metrics appear in one of the following three time frames. Click the clock icon next to the Include Current Data toggle to see the actual latency value for each metric on a report.

| Time Frame | Metrics |
| --- | --- |
| Under 10 minutes | Instances and page views on traffic variables |
| Between 10 and 35 minutes | Conversion events, Instances and page views on conversion variables |
| Between 45 and 120 minutes | All other data, such as visits, unique visitors, and participation |

Because some of the data that is displayed on the current data view has not been fully processed, you can see a difference between values reported on the current data view and the finalized view. On trended reports, the data difference is typically within 1%.

## Calculated Metrics

Since calculated metrics can be created using metrics that have different latency, some recent values might be calculated using incomplete data in the current data view.

For example, you create the calculated metric 'Page Views per Visit using the formula `Page Views divided by Visits`. Page Views typically appear within 10 minutes, and Visits typically appear within 2 hours, calculated metrics within this latency window are calculated using incomplete metrics. If you post a new page that gets 4000 hits from 4000 different visits over a 2 hour time frame, the latency difference between these metrics can cause incomplete calculations.

This data difference is most visible when reporting on new values or using short time frames. When a report uses longer date ranges, the latency differences that occur in the last few hours of reporting are unlikely to have any noticeable impact on calculated metrics.

If you have calculated metrics that might be impacted by these differences, either turn current data off or use metrics with the same expected latency window.

## Downloaded Reports

When you download a report with the current data view enabled, the report is queued, generated, and then returned to the browser. If data is collected while the report is generating, that data appears in the report. This window of time can lead to the downloaded report having slightly more data.
