---
description: Steps that describe how to create an anomaly detection request in report builder.
title: Configure an anomaly detection request
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
---
# Configure an anomaly detection request

To create an anomaly detection request in report builder:

1. Select a trended report, such as a **[!UICONTROL Site Metrics]** > **[!UICONTROL Traffic]** report.
1. In the [!UICONTROL Apply Granularity] menu, select **[!UICONTROL Day]**.

   >[!NOTE]
   >
   >The [!UICONTROL Anomaly Detection] menu is available only when you select Day granularity. The previous 30 days of data is used as the statistical data training period, regardless of the date range you select.

1. After configuring date ranges, click **[!UICONTROL Next]**.

   Step Result 1. On the Request Wizard: Step 2 of 2, add a metric, such as **[!UICONTROL Visits]**.

   Step Result 1. For the added metric, click the **[!UICONTROL None]** link.

   ![Step Result](assets/anomaly_select.png)

1. Select **[!UICONTROL Anomaly Detection]** > **[!UICONTROL `<selection>`]**.

   ![Step Info](assets/anomaly_visit.png)

   When you select one of these options, the system creates Anomaly Detection copies of the original metric. For example, for the Visit metric, a Lower Bound Visit metric is added to the [!UICONTROL Metric] group.
1. Click **[!UICONTROL Finish]** and select the cell for output to Excel.

   See [Anomaly Detection](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) for definitions.
