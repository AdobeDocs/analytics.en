---
description: You can view and analyze data anomalies contextually, within Analysis Workspace.
seo-description: You can view and analyze data anomalies contextually, within Analysis Workspace.
seo-title: Anomaly Detection
title: Anomaly Detection
uuid: 69184f2d-62cf-433a-858d-4fd7d25abc24
index: y
internal: n
snippet: y
translate: y
---

# Anomaly Detection


>[!IMPORTANT]
>
>Anomaly Detection has been removed from the Reports &amp; Analytics feature set and is now available only via Analysis Workspace. Note that Adobe Analytics Select and Adobe Analytics Foundation customers have access only to “daily-granularity” Anomaly Detection in Workspace. For more information, see[ Anomaly Detection and Contribution Analysis Entitlements](../../analysis_workspace_bucket/virtual-analyst/contribution-analysis/ca_tokens.md#section_9278D58F21A840AA9B1ED1BD07A1EF0A). 



Anomaly Detection provides a statistical method to determine how a given metric has changed in relation to previous data. 

Anomaly Detection allows you to separate "true signals" from "noise" and then identify potential factors that contributed to those signals or anomalies. In other words, it lets you identify which statistical fluctuations matter and which don't. You can then identify the root cause of a true anomaly. Furthermore, you can get reliable metric (KPI) forecasts. 

Examples of anomalies you might investigate include: 

* Drastic drops in average order value
* Spikes in orders with low revenue
* Spikes or drops in trial registrations
* Drops in landing page views
* Spikes in video buffer events
* Spikes in low video bit-rates
Both Anomaly Detection and [ Contribution Analysis](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_main.html) are core workflows in Analysis Workspace. You can run Contribution Analysis against any daily anomaly and embed the result in your Analysis Workspace project. 

Analysis Workspace's anomaly detection algorithm includes 

* Support for hourly, weekly, and monthly granularity, in addition to the existing daily granularity.
* Awareness of seasonality (such as "Black Friday") and holidays.
