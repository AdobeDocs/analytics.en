---
description: Steps that describe how to create an anomaly detection request in report builder.
seo-description: Steps that describe how to create an anomaly detection request in report builder.
seo-title: Configure an anomaly detection request
solution: Analytics
title: Configure an anomaly detection request
topic: Report builder
uuid: 0042305f-050e-4846-a43b-95c0573ec244
index: y
internal: n
snippet: y
translate: y
---

# Configure an anomaly detection request


>1. Select a trended report, such as a  ** [!UICONTROL  Site Metrics] ** > ** [!UICONTROL  Traffic] ** report.
>1. In the [!UICONTROL  Apply Granularity] menu, select ** [!UICONTROL  Day] **.

>   >[!NOTE]
>   >
>   >The [!UICONTROL  Anomaly Detection] menu is available only when you select Day granularity. The previous 30 days of data is used as the statistical data training period, regardless of the date range you select. 
>
>1. After configuring date ranges, click ** [!UICONTROL  Next] **.

>1. On the Request Wizard: Step 2 of 2, add a metric, such as ** [!UICONTROL  Visits] **.

>1. For the added metric, click the ** [!UICONTROL  None] ** link.

>       ![Step Result](../../../assets/anomaly_select.png) 
>1. Select  ** [!UICONTROL  Anomaly Detection] ** > ** [!UICONTROL  &amp;lt;selection&amp;gt;] ** .
>   ![Step Info](../../../assets/anomaly_visit.png) 
>

>       When you select one of these options, the system creates Anomaly Detection copies of the original metric. For example, for the Visit metric, a Lower Bound Visit metric is added to the [!UICONTROL  Metric] group. 
>1. Click ** [!UICONTROL  Finish] ** and select the cell for output to Excel.

>       See [ Anomaly Detection ](../../../analysis_workspace_bucket/virtual-analyst/anomaly_detection.md#concept_9476D6C093334B1A8044AE63835BDBE7) for definitions. 
