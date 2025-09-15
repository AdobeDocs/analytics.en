---
description: Understand how to use alerts tp allow for granular control over notifications, and integration with anomaly detection.
title: Alerts Overview
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
---
# Alerts overview

Alerts in Adobe Analytics allow you to be notified based on changed percentages or specific data points. 

Depending on your Adobe Analytics package, you can also use alerts to be triggered based on anomaly thresholds. These alerts (also known as "Intelligent Alerts"), provide granular controls that integrate with [Anomaly Detection](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md), triggering when you need them most.

Alerts let you:

* Preview how often an alert will trigger
* Send alerts by e-mail or SMS with links to auto-generated Analysis Workspace projects
* Create "stacked" alerts that capture multiple metrics in a single alert
* Build alerts based on anomalies (90%, 95%, 99%, 99.75%, and 99.9% thresholds; % change; above/below) (Available only to Adobe Analytics customers with a Select, Prime, or Ultimate package)

The following video tutorial provides a basic overview of alerts: [Alerts](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## Anomaly lookback for alerts

>[!NOTE]
>
>Using alerts with anomaly detection (also known as _Intelligent Alerts_) is available only to organizations with a Adobe Analytics Prime or Ultimate package.

If an alert uses anomaly detection, the training period varies based on the granularity selected for the alert.

* Monthly granularity: 15 months + same range last year
* Weekly granularity: 15 weeks + same range last year
* Daily granularity: 35 days + same range last year
* Hourly granularity: 336 hours

For more information, see [Statistical techniques used in Anomaly Detection](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Create alerts

For information about how to create alerts in Adobe Analytics, see [Create alerts](/help/components/alerts/alert-builder.md).

>[!IMPORTANT]
>
>Using timestamped data to create alerts can cause alerts to fire incorrectly. Adobe recommends using non-timestamped data for alerts.

## Manage alerts

You can manage existing alerts in the Alerts manager. You can perform various management tasks on alerts, such as tagging, renaming, deleting, and more.

For more information about how to manage existing alerts in Adobe Analytics, see [Manage alerts](/help/components/alerts/alert-manager.md).
