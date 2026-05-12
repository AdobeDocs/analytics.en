---
description: All bookmarked reports and dashboard reports are now listed as dimensions in the Request Wizard Step 1 and can be imported as Report Builder requests.
title: Import bookmarked reports and dashboard reportlets
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
TQID: https://experienceleague.adobe.com/dnOYs7eOvv15K73EPrfRegz1vH9-B5p8xI8d86vPYe4
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
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
    internal-label: Report Builder
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Import bookmarked reports and dashboard reportlets

{{legacy-arb}}

All bookmarked reports and dashboard reports are now listed as dimensions in the Request Wizard Step 1 and can be imported as Report Builder requests.

When you select a bookmarked report, the Request Wizard populates all the dimensions and metrics that define this bookmarked report. The date range, granularity and selected segment are also updated based on the selected bookmark.

This is how the Request Wizard Step 1 shows a dashboard and its reportlets:

![Screenshot showing the Request Wizard Step 1 of 2 highlighting Retrieve your Dashboards and Retrieve your Bookmarks.](assets/import_dashboard_reportlet.png)

When you click **[!UICONTROL Retrieve your Dashboards]** or **[!UICONTROL Retrieve your Bookmarks]**, your existing dashboard and/or bookmark data is retrieved and pasted in the worksheet.

>[!NOTE]
>
>Only data is imported, so if the bookmark contains a chart, or if the dashboard reportlet consists of only a chart, only the data that is used to populate the chart is imported.

Once you have created a request by importing a dashboard reportlet (or a bookmark), the request will then be associated to the reportlet's (or bookmark's) primary dimension. As a result, if you edit the request, the tree view no longer selects the dashboard reportlet tree view node (or bookmark node): it selects its primary dimension instead.

