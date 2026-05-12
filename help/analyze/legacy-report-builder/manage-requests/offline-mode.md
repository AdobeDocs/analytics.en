---
description: Learn how to use offline mode to return placeholder data.
title: How to enable offline mode
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
TQID: https://experienceleague.adobe.com/HKk--fSRTABpRb8Q9yOeySHyAVSR-W2Ktzldmp7UeJQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Offline mode for creating and editing requests

{{legacy-arb}}

Offline mode returns placeholder data to speed up the process of creating and editing requests.

When you create or edit a new request, Report API calls are made to retrieve the response. Sometimes these calls slow down the request creation process because you have to wait for the data to return before going to the next step. Offline mode returns placeholder data only and API are not made.

To enable offline mode

1. Click **[!UICONTROL Options]** in the Report Builder menu.

   ![Screenshot of the Options screen with offline ode selected.](assets/offline_mode.png)

1. Check the checkbox next to **[!UICONTROL Turn on offline mode for creating and editing requests]**.
1. In the **[!UICONTROL Display Metric Data as]** field, enter the placeholder data that you want returned in your request. For example, enter "1".
1. Click **[!UICONTROL OK]**.
1. Create and run your request in offline mode using the Request Wizard. The following screenshot shows an example of a request with "1" as the placeholder data.

   ![Screenshot showing the offline mode example using 1 as a placeholder.](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Make sure that you disable Offline Mode before running your requests with real data.
