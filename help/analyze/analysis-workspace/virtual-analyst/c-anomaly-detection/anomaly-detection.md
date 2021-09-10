---
description: You can view and analyze data anomalies contextually, within Analysis Workspace.
title: Anomaly Detection overview
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
feature: AI Tools
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
---
# Anomaly Detection overview

You can view and analyze data anomalies contextually within Analysis Workspace.

>[!VIDEO](https://video.tv.adobe.com/v/25444/?quality=12)

>[!IMPORTANT]
>
>Anomaly Detection has been removed from the Reports & Analytics feature set and is now available only via Analysis Workspace. Note that Adobe Analytics Select and Adobe Analytics Foundation customers have access only to "daily-granularity" Anomaly Detection in Workspace. For more information, see [Anomaly Detection and Contribution Analysis Entitlements](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md#section_9278D58F21A840AA9B1ED1BD07A1EF0A).

Anomaly Detection provides a statistical method to determine how a given metric has changed in relation to previous data.

Anomaly Detection allows you to separate "true signals" from "noise" and then identify potential factors that contributed to those signals or anomalies. In other words, it lets you identify which statistical fluctuations matter and which don't. You can then identify the root cause of a true anomaly. Furthermore, you can get reliable metric (KPI) forecasts.

Examples of anomalies you might investigate include:

* Drastic drops in average order value
* Spikes in orders with low revenue
* Spikes or drops in trial registrations
* Drops in landing page views
* Spikes in video buffer events
* Spikes in low video bit-rates

Both Anomaly Detection and [Contribution Analysis](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) are core workflows in Analysis Workspace. You can run Contribution Analysis against any daily anomaly and embed the result in your Analysis Workspace project.

Analysis Workspace's anomaly detection algorithm includes

* Support for hourly, weekly, and monthly granularity, in addition to the existing daily granularity.
* Awareness of seasonality (such as "Black Friday") and holidays.
