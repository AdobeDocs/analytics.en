---
description: Resources and links for the Reporting API.
title: Analytics Reporting API
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
---
# Analytics Reporting API

Documentation for the Adobe Analytics APIs are on [Adobe I/O](https://adobe.io/analytics-apis/docs).

## Comparison of Analytics APIs

| **API Type** | **Fully Processed** | **Real-Time** | **Livestream** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **Description** | Fully-processed, finalized data that is available in all Analytics interfaces. | Partially-processed, limited metrics available within seconds of collection. | Partially-processed hit data available within seconds of collection. | Fully-processed, finalized data that is used for pulling large data exports. |
| [**Latency**](/help/technotes/latency.md) | 30-90 minutes | Seconds - 10 minutes | Seconds - 10 minutes | 90+ minutes |
| **Processing Completion** | Full | Partial | Partial | Full |
| **Reporting Interfaces** | Analysis Workspace, Reports & Analytics, Report Builder, API | Real-Time report in Reports & Analytics, Report Builder, 1.4 API | API only | Data Warehouse, API |
| **Data granularity** | Summarized | Summarized | Hit level | Summarized |
| **Visitor Profile processing** | Yes | No | No | Yes |
| **Segment support** | Yes | No | No | Partial |
