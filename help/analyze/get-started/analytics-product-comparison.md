---
description: System requirements and a comparison of Analysis Workspace, Report Builder, Data Warehouse, and Data Workbench
title: Analytics product comparison and requirements
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
---
# Analytics product comparison and requirements

This page contains a comparison of various Adobe Analytics products: Analysis Workspace, Report Builder, Data Warehouse, Data Feeds and Analytics API 2.0.

For information on which Adobe Analytics product to use, see [Which Adobe Analytics tool should I use?](/help/analyze/get-started/which-analytics-tool.md).

| Product Name & Help Link | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/rb-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Feeds](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **Access method** | [Browser](/help/analyze/get-started/sys-reqs.md) | [MS Excel for Windows](/help/analyze/legacy-report-builder/setup/system-requirements.md) | Setup through the browser. [Learn more](/help/analyze/get-started/sys-reqs.md)  | Setup through the browser. [Learn more](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API tools. Login with Adobe Developer credentials. [Learn more](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **Data granularity** | Aggregated |  Aggregated | Aggregated | Hit | Aggregated |
| **Experience Cloud ID (ECID) available** | No |  No | Yes | Yes | No |
| **Timestamp available** | No | No | No | Yes | No |
| **Level of processing** | Fully-processed |  Fully-processed, with separate [real-time report](/help/admin/tools/manage-rs/edit-settings/realtime/realtime.md) | Fully-processed |  Fully-processed | Fully-processed |
| **Admin bot filter data included** <br> [Learn more](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) | No | Yes - separate bot report | No | No | No |
| **Low traffic (Uniques exceeded) appears** <br> [Learn more](/help/technotes/low-traffic.md) | Yes | Yes | No | No | Yes |
| **Visible row limit (before pagination)** | 400 | 50000 | Unlimited | Unlimited | 50000 |
| **Multiple report suites** | [Yes](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) |  Yes | No | Yes | No | Yes |
| **Number of breakdowns** | Unlimited | Up to 2 | Unlimited | Unlimited | Unlimited, run across multiple queries |
| **Segmentation** <br> [Learn more](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Yes | Yes | Yes, with [limitations](/help/components/segmentation/seg-reference/seg-compatibility.md) | No | Yes |
| **Calculated metrics** <br> [Learn more](/help/components/c-calcmetrics/cm-overview.md) | Yes, with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Yes, with Attribution | Yes |No | Yes, with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Marketing Channels** <br> [Learn more](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Yes | Yes | Yes | Yes - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Yes |
| **Cohort analysis** | [Yes](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Yes | No | No | No |
| **Attribution** | Yes, with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Limited | No | No | Yes, with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | No |
| **Curation** <br> [Learn more](/help/analyze/analysis-workspace/curate-share/curate.md) | Yes - Project and Virtual report suite | No | No | No | Yes - Virtual report suite only |
| **Project sharing** <br> [Learn more](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Yes, with project roles | Yes | No | No | No |
| **Scheduled delivery** | Yes | Yes | Yes | Yes | No |
| **Delivery destinations** | Email | Email, FTP, SFTP, [publishing to Microsoft PowerBI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC, and Email | Amazon S3, Azure RBAC, Azure SAS, and Google Cloud Platform  | - |
| **Virtual report suite report time processing** <br> [Learn more](/help/components/vrs/vrs-report-time-processing.md) | Yes | No | No | No | Yes |
