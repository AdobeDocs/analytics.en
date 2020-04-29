---
description: Adobe Analytics provides a flexible reporting interface that lets you generate a variety of complex reports. While most reports generate very quickly, you might encounter reports that timeout or fail to generate successfully. To help avoid report generation failures, this section explains many factors that impact report generation speed. Understanding this information can help you structure reports so they are more likely to generate successfully.
keywords: best practices;failure;timeout;troubleshooting;slow
title: Reporting Best Practices and Troubleshooting
topic: Reports
uuid: d4eef0a3-1d26-4460-8a2b-962001c9f846
---

# Reporting Best Practices and Troubleshooting

Adobe Analytics provides a flexible reporting interface that lets you generate a variety of complex reports. While most reports generate very quickly, you might encounter reports that timeout or fail to generate successfully. To help avoid report generation failures, this section explains many factors that impact report generation speed. Understanding this information can help you structure reports so they are more likely to generate successfully.

>[!NOTE]
>These recommendations apply to Reports & Analytics, Ad Hoc Analysis, and Report Builder.
>They do not apply to Analysis Workspace, which has its own set of [best practices](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md). They also do not >apply to Data Warehouse [best practices](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse-bp.html). An additional set of 
>[best practices](https://www.adobe.io) is available for the Adobe Analytics Reporting API.

## Report Timeouts and Request Queue {#section_A42AD7E487C749B7B879BAFA814FFEF9}

**Timeouts**

A single report is broken into multiple requests (one per breakdown), and each request is subject to an individual timeout. Scheduled reports are granted longer timeout periods and are more likely to succeed than reports that are generated directly in a user interface.

**Report Suite Queue**

Each report suite maintains a separate queue of requests. If many reports are requested simultaneously, even from separate users, a small number of reports are generated simultaneously. As reports complete, remaining reports are generated in the order in which they were received. As a result, if a large number of complex reports are already in the report suite queue, a report that typically generates quickly might time out.

## Factors that Affect Report Speed {#section_6BA937EB6CEC4CBCB71FAAD32F031DC2}

The following factors contribute to longer report generation times. Increasing one of these factors might not result in a timeout for that report, but it might delay other reports in the report suite queue and cause a subsequent report to timeout.

**Report Time Range**

The largest factor that affects report generation time is the number of months requested. Reducing the number of months from three to one decreases generation time significantly, but reducing the time range from one month to one week does not have a large impact on report generation time.

**Number of metrics**

As the number of metrics increases, the report run time increases. Removing metrics often improves report generation time.

**Number of breakdowns**

Within a report, each breakdown represents a separate request. While individual requests may complete quickly, running thousands of breakdowns in a single report can significantly slow down report generation time and affect the report suite queue.

**Segment complexity**

Segments that consider many dimensions or have many (24+) rules increase the processing impact and increase the report generation time.

**Number of unique values**

Reports that contain hundreds of thousands of unique values generate more slowly than reports that contain fewer unique values, even if the segment or filter reduces the number of values that ultimately appear in a report. For example, a report that displays search terms typically generates more slowly than other reports, even if a filter is applied to show only search terms that contain a specific value.

## Other Reporting Options {#section_FEF85C7FC6E14755A6086AFFF36E0EB4}

In addition to reducing the time range, number of metrics, and number of breakdowns in a report, the following guidelines help increase reliability of report delivery:

* Use Data Warehouse to request reports that contain many breakdowns or metrics. Data Warehouse is designed to generate these types of reports.
* Schedule reports to run during non-peak hours. This increases the likelihood of a report returning because the request queue for a report suite is more likely to be empty during those times.
* Report Builder can be used to break reports into smaller time ranges and requests that contain fewer metrics. You can then use native Excel functionality to merge data from various requests into a single report.

