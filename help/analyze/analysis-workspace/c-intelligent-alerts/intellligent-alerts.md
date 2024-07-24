---
description: The new Intelligent Alerts system allows for more granular control over alerts and integrates anomaly detection with the alert system.
title: Intelligent Alerts overview
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
---
# Intelligent Alerts overview

Intelligent Alerts (or just "alerts") in Adobe Analytics allow you to be notified immediately when abnormal events occur in your data. 

You can set alerts to be triggered based on anomaly thresholds, changed percentages, or specific data points. Alerts provide granular controls that integrate with [Anomaly Detection](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md), triggering when you need them most.

Intelligent Alerts let you:

* Build alerts based on anomalies (90%, 95%, 99%, 99.75%, and 99.9% thresholds; % change; above/below)
* Preview how often an alert will trigger
* Send alerts by e-mail or SMS with links to auto-generated Analysis Workspace projects
* Create "stacked" alerts that capture multiple metrics in a single alert

The following video tutorial provides a basic overview of alerts: [Intelligent Alerts](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## Anomaly lookback for alerts

If an alert uses anomaly detection, the training period varies based on the granularity selected for the alert.

* Monthly granularity: 15 months + same range last year
* Weekly granularity: 15 weeks + same range last year
* Daily granularity: 35 days + same range last year
* Hourly granularity: 336 hours

For more information, see [Statistical techniques used in Anomaly Detection](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Create alerts

For information about how to create alerts in Adobe Analytics, see [Create alerts](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>Using timestamped data to create alerts can cause alerts to fire incorrectly. Adobe recommends using non-timestamped data for Intelligent Alerts.

## Manage alerts

You can manage existing alerts in the Alerts manager. You can perform various management tasks on alerts, such as tagging, renaming, deleting, and more.

For more information about how to manage existing alerts in Adobe Analytics, see [Manage alerts](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-manager.md).
