---
title: Configure Settings For Report Builder
description: Learn how to configure settings for Report Builder.
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
TQID: https://experienceleague.adobe.com/aHEmYs37KDXtaoAbFiI6WBCvmdhN0RrMWDl-CeEotKw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Report Builder settings


Use the **Settings** pane to configure application-level settings such as the language displayed by the UI or whether or not to work in off-line mode. The settings are applied immediately and they are set for all future sessions until they're changed.

To change Report Builder settings

1. Select the **Settings** icon.

1. Make changes to [enable of disable off-line mode](#off-line-mode), [select a language](#language), or [enable troubleshooting](#troubleshooting).

1. Select **[!UICONTROL Apply]**.

    ![Report Builder date range pane showing the Cancel and Apply button.](./assets/report-builder-settings.png){zoomable="yes"}

## Off-line mode

When you create and edit a data block in off-line mode, data is not retrieved. Instead, simulation data is used so that you can quickly work without waiting for the request to run. When you are back online, select ![Refresh](/help/assets/icons/Refresh.svg) **[!UICONTROL Refresh data block]** or ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Refresh all data blocks]** to refresh the data blocks with actual data.

To enable off-line mode

1. Select ![Setting](/help/assets/icons/Setting.svg).

1. Toggle **[!UICONTROL Enable off-line mode]** on.

1. Enter a positive integer in the **[!UICONTROL Display metric data]** as field.

1. Select **[!UICONTROL Apply]**.


## Language

You can choose the language for the Report Builder interface. All supported Customer Journey Analytics languages are available.

To select the language used in the Report Builder interface:

1. Select a language from the **[!UICONTROL Language]** drop-down menu.

1. Select **Apply.**

## Troubleshooting

The troubleshoot and help resolve support tickets, enable to log Report Builder requests. In the **[!UICONTROL Report Builder]** panel:

  1. Select ![Setting](/help/assets/icons/Setting.svg).
  1. Select **[!UICONTROL Log report builder request data block(s) to web console]**. <br/>Requests are send to your web browser console. Refer to the documentation of your web browser how to open the console log as part of the web browser developer tools.
