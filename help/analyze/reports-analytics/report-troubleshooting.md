---
title: Reporting best practices and troubleshooting
description: Best practices and troubleshooting tips when generating reports.
keywords: best practices;failure;timeout;troubleshooting;slow
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 1c09f514-42ab-4698-bdee-d1b509da3f11
---
# Reporting best practices and troubleshooting

*This help page refers to Reports & Analytics best practices. For Analysis Workspace, see [Optimize Analysis Workspace performance](../analysis-workspace/workspace-faq/optimizing-performance.md). For Data Warehouse, see [Data Warehouse best practices](/help/export/data-warehouse/data-warehouse-bp.md).*

Adobe Analytics provides a flexible reporting interface that lets you generate a variety of complex reports. While most reports generate very quickly, you can encounter reports that timeout or fail to generate. This page explains factors that impact report generation speed. Understanding this information can help you structure reports so that they are more likely to generate successfully.

## Report timeouts and request queue

* **Timeouts**: A single report is broken into multiple requests (one per breakdown), and each request is subject to an individual timeout. Scheduled reports are granted longer timeout periods and are more likely to succeed than reports that are generated directly in a user interface.
* **Report Suite Queue**: Each report suite maintains a separate queue of requests. If many reports are requested simultaneously, even from separate users, a small number of reports are generated simultaneously. As reports complete, remaining reports are generated in the order in which they were received. As a result, if a large number of complex reports are already in the report suite queue, a report that typically generates quickly might time out.

## Factors that affect report speed

The following factors contribute to longer report generation times. Increasing one of these factors typically does not impact performance, but it might delay other reports in the report suite queue and cause a subsequent report to timeout.

* **Report Time Range**: The largest factor that affects report generation time is the number of months requested. Reducing the number of months from three to one decreases generation time significantly, but reducing the time range from one month to one week does not have a large impact on report generation time.
* **Number of metrics**: As the number of metrics increases, the report run time increases. Removing metrics often improves report generation time.
* **Number of breakdowns**: Within a report, each breakdown represents a separate request. While individual requests may complete quickly, running thousands of breakdowns in a single report can significantly slow down report generation time and affect the report suite queue.
* **Segment complexity**: Segments that consider many dimensions or have many (24+) rules increase the processing impact and increase the report generation time.
* **Number of unique values**: Reports that contain hundreds of thousands of unique values generate more slowly than reports that contain fewer unique values, even if the segment or filter reduces the number of values that ultimately appear in a report. For example, a report that displays search terms typically generates more slowly than other reports, even if a filter is applied to show only search terms that contain a specific value.

## Other reporting options

The following guidelines help increase reliability of report delivery:

* Use Data Warehouse to request reports that contain many breakdowns or metrics. Data Warehouse is designed to generate these types of reports.
* Schedule reports to run during non-peak hours. This increases the likelihood of a report returning because the request queue for a report suite is more likely to be empty during those times.
* Report Builder can be used to break reports into smaller time ranges and requests that contain fewer metrics. You can then use native Excel functionality to merge data from various requests into a single report.
