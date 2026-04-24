---
description: Details on the Analysis Workspace template, and reporting in Report Builder.
title: Report on advertising data in Adobe Analytics
feature: Advertising Analytics
exl-id: bbc830d9-e168-471d-a1ba-308277aab415
TQID: https://experienceleague.adobe.com/BOly6gaT1ybHWDppJzhi9ILClvJ9UoLzkGFua1gS1lo
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
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
subfeature_v2:
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
    internal-label: Advertising Analytics
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
    internal-label: Report Builder
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Report on advertising data

This article provide details on the Analysis Workspace report, and the reporting in Report Builder.

>[!NOTE]
>
>Expect to wait at least 24 hours before search engine data starts populating Analytics reports. Analytics reporting does not return data for hourly granularity, because Adobe Advertising data does not support hourly granularity.

## Paid search report {#section_8173F42B2C784F41B9FD82CBB66F9ADF}

This report lets anyone who implements search engine integration get access to search engine data within Analytics. You can access it via **[!UICONTROL Workspace]** > **[!UICONTROL Reports]** > **[!UICONTROL Acquisition]** > **[!UICONTROL Advertising Analytics: paid search]**

>[!NOTE]
>
>The Paid search report is visible to all customers, even if you have not implemented any Advertising Accounts. If you try to open the Paid search report for a company that is not provisioned, an error message will explain that you have not configured any search engine account. Select **[!UICONTROL Configure Now]**, which takes you to the [Advertising Account Setup](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) screen.

![](assets/aa_aw.png)  ![](assets/aa_aw2.png) ![](assets/aa_aw3.png) ![](assets/aa_aw4.png)  ![](assets/aa_aw5.png) ![](assets/aa_aw6.png)

| Table/Visualization | Description |
|--- |--- |
| Advertising Trends | Daily trended overview for AMO Impressions, AMO Clicks, and AMO Cost. |
| Ad Platforms | Donut chart for cost of top 2 platforms (Google Ads, Microsoft Advertising). |
| Ad Platform Totals | Freeform table of the top platforms broken down by AMO Impressions, AMO Clicks, AMO Costs, AMO Avg. Position, AMO Avg. Quality Score. |
| Accounts | Stacked area of cost. |
| Account Totals | Freeform table of the top accounts broken down by the associated metrics. |
| Campaigns | Bar chart of campaign cost. |
| Campaign Totals | Freeform table of the top campaigns broken down by the associated metrics. |
| Groups | Tree map of cost. |
| Group Totals | Freeform table of the top advertising groups broken down by the associated metrics. |
| Ads | Horizontal bar chart of impressions, clicks, and cost. |
| Ad Totals | Freeform table of the top ads broken down by the associated metrics. |
| Keywords | Scatter chart of impressions, clicks, and cost for all keyword/match type combinations. |
| Keyword Totals | Freeform table of the top keyword/match type combinations broken down by the associated metrics. |

## Report Builder {#section_8E0371CF81144C33990D909685D1726E}

As soon as you have set up an Advertising Analytics account, the Advertising Analytics report is made available.
