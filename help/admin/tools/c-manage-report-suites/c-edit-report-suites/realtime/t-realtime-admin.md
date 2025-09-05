---
description: Administrative steps for setting up Real-Time reports.
title: Real-time reports configuration
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c

---
# Real-time reports configuration

Administrative steps for setting up Real-Time reports.

Setting up real-time reports in Adobe Analytics consists of selecting the report suite and configuring up to 3 reports for it. By default, all users have access to Real-Time reports.

1. Select the report suite for which you want to enable real-time reports.

   Navigate to **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]**.
   
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.

1. Set up real-time data collection for up to three reports, with one metric and three dimensions or classifications per report.

   ![](/help/admin/tools/c-manage-report-suites/c-edit-report-suites/realtime/assets/real_time_admin.png)

   For information on supported real-time metrics and dimensions, see [Supported Metrics and Dimensions](/help/admin/tools/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md).

   If you have created classifications, they appear indented under the dimension for which they are defined:

   ![](/help/admin/tools/c-manage-report-suites/c-edit-report-suites/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >For a single Real-Time report, we do not currently support enabling duplicate dimensions, even if a different classification is selected for each dimension.

   >[!NOTE]
   >
   >Some dimensions, such as "Search Keyword" or "Product", do not persist in Real-Time like they do elsewhere in Adobe Analytics. When you select a non-persistent metric, this warning appears:

   ![](/help/admin/tools/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. Click **[!UICONTROL Save]**.

   After this initial report setup, it can take up to 20 minutes for the data to begin streaming. From then on, data is immediately available.

1. To view the real-time report, navigate to:

   **[!UICONTROL Workspace]** > **[!UICONTROL Reports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Real-Time]**.

