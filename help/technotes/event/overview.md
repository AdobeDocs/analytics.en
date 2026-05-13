---
title: Analyze data impacted by events
description: Understand how data impacted by an event contributes to overall data quality.
exl-id: 8d81a432-42d6-4f5d-b66a-bb3af7fc4857
feature: Curate and Share
TQID: https://experienceleague.adobe.com/DJoJwtp9CkgrCfA1DwW8rKX2x3ssfzLCo7vCfhdLusg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
    internal-label: Data quality
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Analyze data impacted by events

Sometimes an event can impact data quality in your organization. Examples include:

* A bot sending outlier data, such as millions of dollars in revenue
* Your organization pushed an update to your website that negatively impacted your Analytics implementation
* Other issues that affect data quality or completeness

If your site experienced any kind of data quality issue, you might want to exclude it from reporting to prevent making business decisions on it. Use these sections to gauge the impact of the event on your data, and determine how you want to proceed.

## Determine the cause of an event

If you are not sure why you see a spike or drop in data, see [Troubleshoot spikes/drops in data](spikes-drops.md).

## Analyze and exclude data using segmentation

Adobe Analytics offers a simple and robust way to focus on or exclude data using segmentation. You can use date range dimensions within segments to filter out or focus on those specific dates. See [Exclude specific dates in analysis](segments.md).

## Compare an event to previous date ranges

If you want to learn more about how much impact an event made on your data over time, you can use date comparison in Analysis Workspace. This feature lets you compare data day-by-day, week-by-week, or month-by-month to see how it compares with previous ranges. You can then use this comparison to determine how much an event affects trends. See [Compare dates impacted by an event to previous ranges](compare-dates.md).

## Derive data using calculated metrics

Once you create segments and use date comparison, you can combine both of these concepts to correct trended data using calculated metrics. Include the segments within a calculated metric, then multiply the affected days by the offset found when comparing dates. See [Derive data impacted by events](calcmetrics.md).

## Communicate impact to users in your organization

Once you are prepared with how you intend to handle an event, you can [communicate to users in your organization](communicate.md). Adobe offers several places within Analytics where you can place text to communicate to users what happened and what components they can use.

## Video

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analyze and communicate variations in your data](https://video.tv.adobe.com/v/33316?quality=12&learn=on){target="_blank"} for a demo video.

* **0:27**: Exclude data using segmentation
* **2:55**: Compare an event to previous ranges
* **8:42**: Derive data using calculated metrics
* **11:46**: Communicate impact to users

>[!ENDSHADEBOX]


