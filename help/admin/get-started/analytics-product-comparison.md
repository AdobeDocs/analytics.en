---
description: System requirements and a comparison of Analysis Workspace, Reports & Analytics, Report Builder, Data Warehouse, and Data Workbench
title: Analytics product comparison and requirements
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
---
# Analytics product comparison and requirements

This page contains a comparison of various Adobe Analytics products: Analysis Workspace, Reports & Analytics, Report Builder, Data Warehouse, Data Workbench, Data Feeds and Analytics API 2.0.

For information on which Adobe Analytics product to use, see [Which Adobe Analytics tool should I use?](/help/admin/get-started/which-analytics-tool.md).

| Product Name & Help Link | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports & Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html) | [Data Feeds](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Access method** | [Browser](/help/admin/get-started/sys-reqs.md) | [Browser](/help/admin/get-started/sys-reqs.md) | [MS Excel for Windows](/help/analyze/report-builder/setup/system-requirements.md) | Setup through the browser. [Learn more](/help/admin/get-started/sys-reqs.md) | [Windows 64 bit](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html) | Setup through the browser. [Learn more](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API tools. Login with Adobe Developer credentials. [Learn more](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **Data granularity** | Aggregated | Aggregated | Aggregated | Aggregated | Hit | Hit | Aggregated |
| **Experience Cloud ID (ECID) available** | No | No | No | Yes | Yes | Yes | No |
| **Timestamp available** | No | No | No | No | Yes | Yes | No |
| **Level of processing** | Fully-processed | Fully-processed, with separate [real-time report](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) | Fully-processed, with separate [real-time report](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) | Fully-processed | Fully-processed | Fully-processed | Fully-processed |
| **Admin bot filter data included** <br> [Learn more](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md) | No | Yes - separate bot report | Yes - separate bot report | No | No | No | No |
| **Low traffic (Uniques exceeded) appears** <br> [Learn more](/help/technotes/low-traffic.md) | Yes | Yes | Yes | No | No | No | Yes |
| **Visible row limit (before pagination)** | 400 | 200 | 50000 | Unlimited | Unlimited | Unlimited | 50000 |
| **Multiple report suites** | [Yes](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Yes, with limitations | Yes | No | Yes | No | Yes |
| **Number of breakdowns** | Unlimited | Up to 2 | Up to 2 | Unlimited | Unlimited | Unlimited | Unlimited, run across multiple queries |
| **Segmentation** <br> [Learn more](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Yes | Yes | Yes | Yes, with [limitations](/help/components/segmentation/seg-reference/seg-compatibility.md) | Yes | No | Yes |
| **Calculated metrics** <br> [Learn more](/help/components/c-calcmetrics/cm-overview.md) | Yes, with [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Yes | Yes | No | Yes | No | Yes, with [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Marketing Channels** <br> [Learn more](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Yes | Yes | Yes | Yes | Yes | Yes - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Yes |
| **Cohort analysis** | [Yes](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | No | No | No | Yes | No | No |
| **Attribution** | Yes, with [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Limited | Limited | No | Yes | No | Yes, with [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Virtual Analyst features** <br> [Learn more](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | Yes | No | No | No | No | No | Yes |
| **Curation** <br> [Learn more](/help/analyze/analysis-workspace/curate-share/curate.md) | Yes - Project and VRS | No | No | No | No | No | Yes - VRS only |
| **Project sharing** <br> [Learn more](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Yes, with project roles | Yes | Yes | No | Yes | No | No |
| **Scheduled delivery** | Yes | Yes | Yes | Yes | No | Yes | No |
| **Delivery destinations** | Email | Email | Email, FTP, SFTP, [publishing to Microsoft PowerBI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | Email, FTP. Reach out to Customer Care for additional destination support including SFTP, Azure Blob, Amazon S3 | - | FTP, SFTP, Azure Blob, Amazon S3 | - |
| **VRS report time processing** <br> [Learn more](/help/components/vrs/vrs-report-time-processing.md) | Yes | No | No | No | No | No | Yes |
