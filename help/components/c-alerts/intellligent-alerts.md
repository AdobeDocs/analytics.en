---
description: The Intelligent Alerts system allows for more granular control over alerts and integrates anomaly detection with the alert system.
title: Intelligent alerts
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
---
# Intelligent alerts

The Intelligent Alerts system allows for more granular control over alerts and integrates anomaly detection with the alert system.

Here is a video overview:

>[!VIDEO](https://video.tv.adobe.com/v/25446/?quality=12)

## Overview {#section_6AC8CA81DEA94E99B0F192B60D0FDF03}

>[!IMPORTANT]
>
>Intelligent Alerts are available to Adobe [!DNL Analytics] Prime and Adobe [!DNL Analytics] Ultimate customers only.

Intelligent Alerts let you

* Build alerts based on anomalies (90%, 95%, 99%, 99.75%, and 99.9% thresholds; % change; above/below).
* Preview how often an alert will trigger.
* Send alerts by e-mail or SMS with links to auto-generated Analysis Workspace projects.
* Create "stacked" alerts that capture multiple metrics in a single alert.

Components of the alert system include: Alert Builder, Alert Manager, Alert Preview, and better in-context access to creating alerts. The old alert system user interface will no longer be available, but the alerts will be migrated. Some legacy alert features [are no longer available](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/alerts.html).

There are three ways get to the Alert Builder:

* By using the following shortcut in Analysis Workspace:

  `ctrl (or cmd) + shift + a` 
* By going directly to the Alert Builder:  **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]** .
* By selecting one or more freeform table line item/s, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**. This will open the Alert Builder and will pre-populate the builder with the appropriate metrics and filters applied from the table. You can then edit the alert, if needed.

  ![](assets/create-alert-from-selection.png)


## FAQ: How alerts are calculated and triggered {#trigger}

The % thresholds are standard deviations. For example, 95% = 2 standard deviations and 99% = 3 standard deviations. Depending on the time granularity you choose, [different models](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) are used to calculate how far away (how many standard deviations) each data point is from the norm. If you set a lower threshold (such as 90%), you will get more anomalies than if you set a higher threshold (99%). 99.75% & 99.99% thresholds were introduced specifically for the hourly granularity so that it wouldn't trigger as many anomalies.

+++ How far back does the alert's anomaly detection go to determine data anomalies?

The training period varies based on the granularity selected. See Statistical Techniques used in <a href="/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md">Anomaly Detection</a> for more detail. Here is a summary: 

* Monthly = 15 months + same range last year
* Weekly = 15 weeks + same range last year
* Daily = 35 days + same range last year
* Hourly = 336 hours

+++

+++ To be alerted to only a dip in behavior or only a spike in behavior, can I use the anomaly feature or do I need to use an absolute value? 

Using the absolute value would still trigger alerts on dips as well as spikes. You cannot isolate alerts for just dips or just spikes. 

+++

+++ Can I configure alerts to trigger only during certain hours of the day (such as business hours vs. non-business hours)?  

Currently, no.

+++

+++ Can I get a table of the "expected values" that comprise the dotted line, or some sort of output of what those values are?

Not in Workspace, but you can in Report Builder. See [this video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/exporting/report-builder/anomaly-detection-in-report-builder.html) on Anomaly Detection in Report Builder. 

Keep in mind that Report Builder uses less sophisticated anomaly detection methods. It uses a fixed 30-day training period, fixed 95% interval.

+++
