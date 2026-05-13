---
description: Discover everything you can do with Advertising Analytics, including permissions required, and available dimensions and metrics.
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
TQID: https://experienceleague.adobe.com/BY9Zpnhu8FzGDHePD-MuWtyMWOuJKRgC-wTr42-rlyU
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
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
    internal-label: Advertising Analytics
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
    internal-label: Report Builder
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
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
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
---
# Advertising Analytics

Advertising Analytics lets you see all your Google Ads and Microsoft Advertising paid search data side by side within Adobe Analytics. Previously, any Google Ads or Microsoft Advertising data would have to be viewed in Adobe Advertising or in each respective ad interface. You can now get impression, click, and cost data directly from search engines as well as AMO ID Instances (Click Instances). 

By bringing the data from these search engines together in Adobe Analytics, you can analyze that same data by using the power of Analysis Workspace. A new [Paid Search Performance](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) template in Workspace facilitates this analysis.

![](assets/aa_aw.png)

This integration is aimed at the following audiences:

* The **Analyst** who needs to collect performance reports for the Paid Search Marketer.
* The **Paid Search Marketer** who seeks answers to these questions: How much traffic am I sending to our site and are customers converting? What are my cost effective ad campaigns?


## Prerequisites {#prerequisites}

* Advertising Analytics is available for Adobe Analytics [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html), and [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) SKUs only.
* This functionality is available for customers that do not use Adobe Advertising.
* You must be an Adobe Analytics Administrator to have access to Advertising Analytics or be belong to a product profile that has been [granted access](/help/integrate/c-advertising-analytics/overview.md#permissions) to Advertising Analytics.
* For any report suite where you want to view Google Ads or Microsoft Advertising search data, you must [enable those report suite/s for Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**).
* You need login credentials for a user with edit permissions to the search account/s which you want to integrate with Adobe Analytics, such as a Google Account ID and password.
* In the case of Microsoft Advertising, you also need the [[!UICONTROL Account ID] and [!UICONTROL Manager Account ID]](c-adanalytics-workflow/aa-locate-account-id.md).

## Advertising Analytics Permissions {#permissions}

Analytics has two permissions that are automatically granted to Analytics admins. Admins can then choose to grant these permissions to non-admins.

| Permission | Definition | Grant permission if you are logged in to Adobe Experience Cloud |
| --- | --- | --- |
| Advertising Analytics Management | Lets users set up/edit/view advertising search accounts. | Log in to [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Products] > [!UICONTROL Adobe Analytics] > [!UICONTROL Product Profile] > [!UICONTROL Permissions] tab > [!UICONTROL Analytics Tools] > [!UICONTROL Advertising Analytics Management] |
| Advertising Analytics Configuration | Lets users configure report suites to be provisioned for Advertising Analytics. | Log in to [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Products] > [!UICONTROL Adobe Analytics] > [!UICONTROL Product Profile] > [!UICONTROL Permissions] tab > [!UICONTROL Analytics Tools] > [!UICONTROL Advertising Analytics Configuration] |

## Advertising Analytics dimensions and metrics {#dimensions-metrics}

Advertising Analytics adds the following dimensions and metrics to Analysis Workspace, Report Builder, and the Analytics Reporting API.

### Dimensions

>[!IMPORTANT]
>
>This integration creates a new set of dimensions through classifications of the AMO ID variable. These new dimensions do not impact or modify your existing marketing channels or campaign tracking variable dimensions. The AMO ID is connected to a visitor's profile when a visitor land on the site from a paid search ad. As such, the AMO dimensions can be used to break down both the AMO metrics provided by this integration as well as any data captured downstream by the visitor (visits, visitors, page views, bounce rate, orders, revenue, custom events, etc). They can also be broken down by other dimensions when reporting on other onsite metrics.
>
>The classifications for these metrics are updated daily. As such, if you make changes to the meta data in a search engine, you may not see those changes reflect until the following day when the classifications are updated.

| Classification (dimension) name | Definition |
| --- | --- |
| **[!UICONTROL Keyword MatchType (AMO ID)]** | The keyword match type. Values typically will be either broad, phrase, exact, or no value if the Ad type does not have a match type. |
| **[!UICONTROL Ad Platform (AMO ID)]** | The search engine name. Values can include "Google AdWords" or "Microsoft Bing Ads". |
| **[!UICONTROL Account (AMO ID)]** | The name of the search engine account that is being tracked. |
| **[!UICONTROL Campaign (AMO ID)]** | The name of the campaign in your search engine account. |
| **[!UICONTROL Ad Group (AMO ID)]** | The name of the ad group in your search engine campaigns. |
| **[!UICONTROL Ad (AMO ID)]** | The Ad Title + Ad Description that is used on your ad. |
| **[!UICONTROL Keyword (AMO ID)]** | The Keyword value from you search engine account. |
| **[!UICONTROL Match Type (AMO ID)]** | The Keyword Match Type assigned to your keyword. Values typically will be either broad, phrase, exact, or no value if the Ad type does not have a match type. |
| **[!UICONTROL Ad Type (AMO ID)]** | The type of ad being served, which is typically "Text Ad". |
| **[!UICONTROL Ad Title (AMO ID)]** | The Title object used in your Ad. |
| **[!UICONTROL Ad Description (AMO ID)]** | The Ad Description object used in your Ad. |
| **[!UICONTROL Ad Display URL (AMO ID)]** | The Ad Display URL object used in your Ad. |
| **[!UICONTROL Ad Destination URL (AMO ID)]** | The landing page URL or Final URL assigned to your Ad. |
| **[!UICONTROL Network (AMO ID)]** | The network the Ad is being served on. For Advertising Analytics, this value is always "Search". |
| **[!UICONTROL Placement (AMO ID)]** | The managed placement website (for content networks). Only managed placements use this dimension. |
| **[!UICONTROL Product Target (AMO ID)]** | The name of product target used on PLA ads (not the actual product purchased). |
| **[!UICONTROL Optimization (AMO ID)]** | Not used by Advertising Analytics. It is used only by Adobe Advertising customers. |
| **[!UICONTROL Device (AMO ID)]** | Not used today. Placeholder for potential future product enhancement to indicated target device type (e.g. mobile, desktop) of ad (not the actual device of visitor). |

### Metrics

>[!IMPORTANT]
>
>The metrics provided by Advertising Analytics (listed below) are summary-level data from the search engines. They are not connected to the Analytics visitor profiles. They are only connected to the AMO ID variable and its associated classification dimensions. As such, they should not be reported on by any dimensions/segments other than those based on the AMO ID dimensions. Doing so will result in Analytics displaying zeros for the data. You can include them in calculated metrics with other metrics, but these calculated metric should also be broken down only by the AMO ID dimensions.
>
>These metrics are data sourced on a daily basis so they will not have data for the current day. They also should not be reported on a granularity lower than daily.
>
>There is an AMO ID Instances metric that is set when the AMO ID is set on a landing page (i.e. a Clickthrough). This metric is captured in real time with the landing page hit and is available for breakdowns with other dimensions also set on the landing page.

| Metric name | Definition |
| --- | --- |
| **[!UICONTROL AMO Impressions]** | The number of ad impressions as reported by the search engine. |
| **[!UICONTROL AMO Clicks]** | The number of clicks on ads as reported by the search engine. |
| **[!UICONTROL AMO Cost]** | The cost paid for each keyword/ad as reported by the search engine. |
