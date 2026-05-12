---
description: Administrative steps for setting up Real-Time reports.
title: Real-time reports configuration
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
TQID: https://experienceleague.adobe.com/HTu1UvUUIGK0SzAQWEFBclV-P1JaPCJUp6j5MiYC3A0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Real-time reports configuration

Administrative steps for setting up Real-Time reports.

Setting up real-time reports in Adobe Analytics consists of selecting the report suite and configuring up to 3 reports for it. By default, all users have access to Real-Time reports.

1. Select the report suite for which you want to enable real-time reports.

   Navigate to **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]**.
   
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.

1. Set up real-time data collection for up to three reports, with one metric and three dimensions or classifications per report.

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/real_time_admin.png)

   For information on supported real-time metrics and dimensions, see [Supported Metrics and Dimensions](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md).

   If you have created classifications, they appear indented under the dimension for which they are defined:

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >For a single Real-Time report, we do not currently support enabling duplicate dimensions, even if a different classification is selected for each dimension.

   >[!NOTE]
   >
   >Some dimensions, such as "Search Keyword" or "Product", do not persist in Real-Time like they do elsewhere in Adobe Analytics. When you select a non-persistent metric, this warning appears:

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. Click **[!UICONTROL Save]**.

   After this initial report setup, it can take up to 20 minutes for the data to begin streaming. From then on, data is immediately available.

1. To view the real-time report, navigate to:

   **[!UICONTROL Workspace]** > **[!UICONTROL Reports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Real-Time]**.

