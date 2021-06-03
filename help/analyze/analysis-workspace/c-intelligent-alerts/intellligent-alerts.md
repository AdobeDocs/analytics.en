---
description: The new Intelligent Alerts system allows for more granular control over alerts and integrates anomaly detection with the alert system.
title: Intelligent Alerts overview
uuid: b9bf75ad-bb6f-49fe-8c55-355ea3c50a71
feature: AI Tools
role: Business Practitioner, Administrator
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
---
# Intelligent Alerts overview

Intelligent Alerts allows for more granular control over alerts and integrates anomaly detection with the alert system.

Here is a video tutorial on [Intelligent Alerts](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## Overview

The new Alert Builder and Alert Manager in Analysis Workspace replace the existing alert functionality in Reports & Analytics. Intelligent Alerts let you:

* Build alerts based on anomalies (90%, 95%, 99%, 99.75%, and 99.9% thresholds; % change; above/below)
* Preview how often an alert will trigger
* Send alerts by e-mail or SMS with links to auto-generated Analysis Workspace projects
* Create "stacked" alerts that capture multiple metrics in a single alert

There are four ways get to the Alert Builder:

* Going directly to the Alert Builder:  **[!UICONTROL Components]** > **[!UICONTROL Alerts]**
* Using the keyboard shortcut in Workspace: `Ctrl + Shift + A` (Windows) or `Cmd + Shift + A` (Mac)
* Selecting one or more freeform table line item/s, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**. This opens the Alert Builder and pre-populates the appropriate metrics and filters applied from the table. You can edit the alert if needed.

  ![Create alert from selection](assets/create-alert-from-selection.png)

* From within a Reports & Analytics report, by going to  **[!UICONTROL More]** > **[!UICONTROL Add Alert]** . This opens the alert builder and pre-populates the appropriate metrics and filters applied from the report. You can edit the alert if needed.

  ![Add alert](assets/add-alert.png)

The percent thresholds are standard deviations. For example, 95% = 2 standard deviations and 99% = 3 standard deviations. Depending on the time granularity you choose, [different models](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) are used to calculate how far away (how many standard deviations) each data point is from the norm. If you set a lower threshold (such as 90%), you get more anomalies than if you set a higher threshold (99.75%).

>[!IMPORTANT]
>
>Using timestamped data to create alerts can cause alerts to fire incorrectly. Adobe recommends using non-timestamped data for Intelligent Alerts.

## Anomaly lookback for alerts

If an alert uses anomaly detection, the training period varies based on the granularity selected for the alert.

* Monthly granularity: 15 months + same range last year
* Weekly granularity: 15 weeks + same range last year
* Daily granularity: 35 days + same range last year
* Hourly granularity: 336 hours

See [Statistical techniques used in Anomaly Detection](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) for more information.
