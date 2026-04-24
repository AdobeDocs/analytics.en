---
title: Full Review
description: Review your implementation every 6 months to ensure continued alignment with business needs and KPIs.
feature: Implementation Basics
exl-id: 235fc86e-e1b0-4b1a-a270-0dfba457a832
role: Admin, Leader
TQID: https://experienceleague.adobe.com/YQL-V84ZWAr8NqRp1snYZBgl7-3iIhhxWkWh6KTFKNM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
    internal-label: Alerts
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
    internal-label: Data quality
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Full Review (for reviewing your implementation twice yearly)

Why should you review your implementation every 6 months? Because you need to make sure that your implementation stays aligned with your business needs! You also want to address any issues with data quality while they're small and before they grow into major data issues that could erode stakeholders' confidence. In addition to these Full Reviews every 6 months, you should also be doing [Focused Reviews](/help/implement/review/focused-review.md), after each website release.

## 1. Make sure that your implementation is still fully aligned with our business needs

Meet with the business owner and/or analysts to review the changing business needs. For any needs or measurement opportunities that are not currently being met by your implementation, figure out how to update your KPIs and measurement plans. Remember to record your changes in your [BRD and SDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html#implementation).

## 2. Make sure that your metrics and variables are still functioning well

Briefly review all your metrics and variables, in order of importance to the business, to make sure that the data is collecting correctly. Start with your most crucial metrics and variables – the ones associated with your [top 5 KPIs](/help/implement/review/define-kpis.md#review). To do this:

* Create dashboards to see monthly trended views of your metrics and variables (or set up [alerts](/help/components/alerts/alerts-overview.md) for each one) to ensure you're getting the data you expect, and the data is correct. If you find any discrepancies, examine your data layer, tag manager rules, and processing rules to find out why.
* Re-run the [Analytics Health Dashboard](https://assets.adobe.com/public/8ff304bb-18e0-434b-54d1-39199422ba1c) to monitor broad trends of your metrics and variables.
  
Don't allow your implementation to get bloated with metrics and variables you don't need. Disable metrics or variables that the business no longer needs or uses. You may want to delete or repurpose them later.

## 3. Refresh your KPIs

Now that you have a refreshed view of the business goals, reassess whether you have indeed chosen the 5 *most* important Key Performance Indicators (KPIs). You can only have 5! These KPIs can be metrics such as revenue, or calculated metrics such as revenue per visit, and the metrics can have variables as well. Refer to [Define your Top 5 KPIs](/help/implement/review/define-kpis.md) for more information.
