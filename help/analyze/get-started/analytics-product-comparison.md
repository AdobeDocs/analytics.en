---
description: System requirements and a comparison of Analysis Workspace, Report Builder, Data Warehouse, and Data Workbench
title: Analytics product comparison and requirements
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
TQID: https://experienceleague.adobe.com/VQgK6DUSlz-UA3zk-Q18-QOAI5M6xfK7KqBYwW56j6w
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
    internal-label: Report Builder
  - id: af53ada8-1b7d-4929-ac91-ac971dd20ec7
    internal-label: System requirements
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
  - id: e9cb007b-c8b7-4975-bc81-11a788c535fa
    internal-label: Cohort Analysis
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
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
| **Multiple report suites** | [Yes](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) |  Yes | No | Yes | No |
| **Number of breakdowns** | Unlimited | Up to 2 | Unlimited | Unlimited | Unlimited, run across multiple queries |
| **Segmentation** <br> [Learn more](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Yes | Yes | Yes, with [limitations](/help/export/data-warehouse/segment-compatibility.md) | No | Yes |
| **Calculated metrics** <br> [Learn more](/help/components/calculated-metrics/cm-overview.md) | Yes, with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Yes, with Attribution | Yes |No | Yes, with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Marketing Channels** <br> [Learn more](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Yes | Yes | Yes | Yes - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Yes |
| **Cohort analysis** | [Yes](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Yes | No | No | No |
| **Attribution** | Yes, with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Limited | No | No | Yes, with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Curation** <br> [Learn more](/help/analyze/analysis-workspace/curate-share/curate.md) | Yes - Project and Virtual report suite | No | No | No | Yes - Virtual report suite only |
| **Project sharing** <br> [Learn more](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Yes, with project roles | Yes | No | No | No |
| **Scheduled delivery** | Yes | Yes | Yes | Yes | No |
| **Delivery destinations** | Email | Email, FTP, SFTP, [publishing to Microsoft PowerBI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC, and Email | Amazon S3, Azure RBAC, Azure SAS, and Google Cloud Platform  | - |
| **Virtual report suite report time processing** <br> [Learn more](/help/components/vrs/vrs-report-time-processing.md) | Yes | No | No | No | Yes |
| **Geo and technology reports** | Yes <p>Uses mid values rather than post fields. Visit first-hit logic is based on `post_cust_hit_time_gmt` instead of `visit_page_num=1`. Results might differ from other tools if IP changes mid-visit, hits arrive out-of-order, or visits cross month boundaries.</p> | Yes <p>Uses mid values rather than post fields. Visit first-hit logic is based on `post_cust_hit_time_gmt` instead of `visit_page_num=1`. Results might differ from other tools if IP changes mid-visit, hits arrive out-of-order, or visits cross month boundaries.</p> | Yes <p>Uses post values and `visit_page_num=1` to determine the first hit of the visit. Applies the value from the first hit to all hits in the visit for these dimensions.</p>  | Yes <p>Uses post values and `visit_page_num=1` to determine the first hit of the visit. Applies the value from the first hit to all hits in the visit for these dimensions.</p> | Yes <p>Uses mid values rather than post fields. Visit first-hit logic is based on `post_cust_hit_time_gmt` instead of `visit_page_num=1`. Results might differ from other tools if IP changes mid-visit, hits arrive out-of-order, or visits cross month boundaries.</p> |
