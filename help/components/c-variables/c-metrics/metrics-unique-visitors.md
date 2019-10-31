---
description: In version 14, a unique visitor refers to a visitor who visits a site for the first time within a specified time period. For example, the unique visitor can visit a site ten times in a week, but if the time period is week, a single unique visitor is counted only once for that week. After that week is ended, that unique visitor can be counted again for a different time period.
seo-description: In version 14, a unique visitor refers to a visitor who visits a site for the first time within a specified time period. For example, the unique visitor can visit a site ten times in a week, but if the time period is week, a single unique visitor is counted only once for that week. After that week is ended, that unique visitor can be counted again for a different time period.
seo-title: Unique Visitors
solution: Analytics
title: Unique Visitors
topic: Metrics
uuid: ae210698-99f9-485e-a640-c7520807adc7
---

# Unique Visitors

In version 14, a unique visitor refers to a visitor who visits a site for the first time within a specified time period. For example, the unique visitor can visit a site ten times in a week, but if the time period is week, a single unique visitor is counted only once for that week. After that week is ended, that unique visitor can be counted again for a different time period.

## Differences between version 14 and 15

Version 14 does not remove duplicate [!UICONTROL Visits] and [!UICONTROL Unique Visitors] metrics from classifications-based reports. For example, if two video clips shared the same classification, a single visitor that viewed both clips generated two [!UICONTROL Visits] and [!UICONTROL Unique Visitors] in the classification-based report.

Version 15 removes duplicate [!UICONTROL Visits] and [!UICONTROL Unique Visitors] from the classification-based report. This is a more accurate measure of [!UICONTROL Visits] and [!UICONTROL Visitors], but typically results in a decrease in your [!UICONTROL Visits] and [!UICONTROL Unique Visitors] metrics for classification-based reports, when compared to data collected prior to upgrade.

|  Uses  | Description  |
|---|---|
|  Traffic  | A visitor is a person that comes to your website. Does not require a persistent cookie.  |
|  Conversion  | A visitor is a person that comes to your website. Is counted when a conversion-related event or action occurs.  |
|  Ad Hoc Analysis  | A visitor is a person that comes to your website. Does not require a persistent cookie.  |

See [Unique Visitors Report - Version 15 and Ad Hoc Analysis](../../../components/c-variables/dimensionslist/reports-unique-visitors-v15-dsc.md#concept_877141D6D1E743DA9FAB41C72A8121C7).

>[!MORELIKETHIS]
>
>* [Daily Unique Visitors](/help/components/c-variables/c-metrics/metrics-daily-unique-visitors.md)
