---
description: System requirements and a comparison of Analysis Workspace, Reports & Analytics, Ad Hoc Analysis, Report Builder, Data Warehouse, and Data Workbench
title: Analytics product comparison and requirements
---

# Analytics product comparison and requirements

This page contains a comparison of various Adobe Analytics products: Analysis Workspace, Reports & Analytics, Report Builder, Data Warehouse, Data Workbench, Data Feeds and Analytics API 2.0.

For information on which Adobe Analytics product to use, go [here](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

|Product Name & Help Link|[Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html)|[Reports & Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html)|[Report Builder](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html)|[Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html)|[Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)|[Data Feeds](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html)|[Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)|
|---|---|---|---|---|---|---|---|
**Access method**|[Browser](https://docs.adobe.com/content/help/en/analytics/admin/sys-reqs.html)|[Browser](https://docs.adobe.com/content/help/en/analytics/admin/sys-reqs.html)|[MS Excel for Windows](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/report-builder-setup/system-requirements.html)|Setup through browser. Supported destinations include FTP. Reach out to Customer Care for additional destination support. [Learn more](https://docs.adobe.com/content/help/en/analytics/admin/sys-reqs.html)|[Windows 64 bit](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html)|Setup through the browser. Supported destinations include FTP, SFTP, Azure Blob, S3. [Learn more](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html)|RESTful API tools. Login with Adobe I/O credentials. [Learn more](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)|
**Data format (granularity)**|Aggregated|Aggregated|Aggregated|ECID|Timestamp + ECID|Timestamp + ECID|Aggregated|
**Level of processing**|Fully-processed|Fully-processed, with separate [real-time report](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html)|Fully-processed, with separate [real-time report](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html)|Fully-processed|Fully-processed|Fully-processed|Fully-processed|
**Admin bot filter data included** <br>[Learn more](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html)|No|Yes - separate bot report|Yes - separate bot report|No|No|No|No|
**Low traffic (Uniques exceeded) appears** <br>[Learn more](https://docs.adobe.com/content/help/en/analytics/technotes/low-traffic.html)|Yes|Yes|Yes|No|No|No|Yes|
**Visible row limit (before pagination)**|400|200|50000|Unlimited|Unlimited|Unlimited|50000|
**Multiple report suites**|[Yes](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html)|Yes, with limitations|Yes |No|Yes|No|Yes|
**Number of breakdowns**|Unlimited|Up to 2|Up to 2|Unlimited|Unlimited|Unlimited|Unlimited, run across multiple queries|
"**Segmentation** <br>[Learn more](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html)|Yes|Yes|Yes|Yes, with [limitations](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segment-reference/seg-compatibility.html)|Yes|No|Yes|
**Calculated metrics** <br>[Learn more](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html)|Yes, with [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html)|Yes|Yes|No|Yes|No|Yes, with [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html)|
**Marketing Channels** <br>[Learn more](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-getting-started-mchannel.html)|Yes|Yes|Yes|Yes|Yes|Yes - va_finder, va_closer|Yes|
**Cohort analysis**|[Yes](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html)|No|No|No|Yes|No|No|
**Attribution**|Yes, with [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html)|Limited|Limited|No|Yes|No|Yes, with [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html)|
**Virtual Analyst features** <br>[Learn more](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/overview.html)|Yes|No|No|No|No|No|Yes|
**Curation** <br>[Learn more](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)|Yes - Project and VRS|No|No|No|No|No|Yes - VRS only|
**Project sharing** <br>[Learn more](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/share-projects.html)|Yes, with project roles|Yes|Yes|No|Yes|No|No|
**Scheduled delivery**|Yes|Yes|Yes|Yes|Yes|Yes|No|
**VRS report time processing** <br>[Learn more](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-report-time-processing.html)|Yes|No|No|No|No|No|Yes|
