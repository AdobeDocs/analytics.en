---
description: Administrative steps for setting up Real-Time reports.
title: Configure real-time reports
feature: Real-time
exl-id: 9e7fc67c-71d5-465a-9553-5bb7e02a9bfd
TQID: https://experienceleague.adobe.com/wmZj-F8P4ectiMUnpy9yYT-pviys2m2aBGAVtP5kNNI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Configure real-time reports

The following information contains administrative steps for setting up Real-Time reports.

This consists of selecting the report suite and configuring up to 3 reports for it.

1. Select the report suite for which you want to enable real-time reports.

   1. In Analysis Workspace, select the [!UICONTROL **Workspace**] tab, then select [!UICONTROL **Reports**] > [!UICONTROL **Engagement**] > **[!UICONTROL Real-Time]**.
   
   1. Select the report suite from the drop-down at the top:

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report_suite_selector.png)

      If you try to view real-time reports for a report suite that has not been set up for real-time reporting, a message displays that enables you to set up the report suite.

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/rep_suite_not_set_up.png)

1. Select **[!UICONTROL Configure]** to run the [!UICONTROL Report Suite Manager].

   (Also available under **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.) 

1. Turn on the **[!UICONTROL Enable Real-Time]** setting.
1. Set up real-time data collection for up to three reports, with one metric and three dimensions or classifications per report.

   ![](assets/real_time_admin.png)

   For information on supported real-time metrics and dimensions, see [Supported Metrics and Dimensions](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md).

   If you have created classifications, they appear indented under the dimension for which they are defined:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >For a single Real-Time report, we do not currently support enabling duplicate dimensions, even if a different classification is selected for each dimension.

   >[!NOTE]
   >
   >Some dimensions, such as "Search Keyword" or "Product", do not persist in Real-Time like they do elsewhere in Adobe Analytics. When you select a non-persistent metric, this warning appears:

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. Select **[!UICONTROL Save]** or **[!UICONTROL Save and View Report]**.

   After this initial report setup, it can take up to 20 minutes for the data to begin streaming. From then on, data is immediately available.

1. By default, all users have access to Real-Time reports.
