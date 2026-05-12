---
description: Configure an Experience Cloud mapped report suite for use in Advertising Analytics.
title: Enable report suite for Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
TQID: https://experienceleague.adobe.com/sGEXiz2RiDhf9p-2df76o-XxBERTKPB-O-rZeIb4BBI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Enable report suite for Advertising Analytics

To see any Advertising Analytics search data in Analytics, you need to configure each Experience Cloud-mapped report suite for Advertising Analytics reporting.

1. Navigate to **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

1. Select the report suite that is mapped to your Experience Cloud organization.
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**.

   ![Reporting](assets/aa-reporting.png)

1. Select **[!UICONTROL Unfamiliar with Advertising Analytics? Click here to learn more]** for more information on Advertising Analytics.
   
1. Set the variable allocation and expiration that you want the AMO ID variable to use. Conversion variables (eVars) allow Adobe Analytics to attribute success events to specific variable values. Sometimes, variables encounter more than one value before hitting a success event. For these cases, allocation determines which variable value gets credit for the event.

    | Setting | Definition |
    |--- |--- |
    | **[!UICONTROL Allocation]** | Select between:<br/> **[!UICONTROL Original Value (First)]**: The first value seen gets full allocation credit, no matter what subsequent values for that variable are. <br/>**[!UICONTROL Most Recent (Last)]**: The last value seen gets full allocation credit for the success event, no matter what variables were fired before it.|
    | **[!UICONTROL Expire After]**| Lets you specify a time period, or event, after which the eVar value expires (that is, no longer receives credit for success events).  If a success event occurs after eVar expiration, the None value receives credit for the event (no eVar was active).|

1. Click **[!UICONTROL Enable Advertising Analytics Reporting]** (first time), or **[!UICONTROL Update Advertising Analytics Reporting]** (subsequent times). Your report suite is now ready to receive Advertising Analytics Search data. You are now ready to [create Advertising Accounts](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
