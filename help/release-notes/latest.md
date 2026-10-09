---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
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
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Current Adobe Analytics release notes (October 2026)

**Last update**: October 7, 2026

These release notes cover the October 2026 release period. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes are updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ---- |
| **Read-only permission for the Adobe Analytics MCP server**<br/>Administrators can now give users read-only access to the Adobe Analytics MCP server. The new [!UICONTROL MCP Read-only Access] permission item gives users access to all read-only tools, without letting them create projects, segments, or calculated metrics.<p>The existing [!UICONTROL MCP Access] permission item is renamed to [!UICONTROL MCP Full Access]. Users with this permission keep access to all tools, including tools that create, change, or delete components.</p><p>For more information, see [Set up permissions](https://developer.adobe.com/analytics-mcp/docs/guides/permissions) in the Adobe Analytics MCP server documentation.</p> | | October 6, 2026 |
| **Automatically generate component descriptions** <br/>You can now automatically generate descriptions for dimensions, metrics, calculated metrics, segments, and date ranges. This helps Workspace users understand which components to use, especially in organizations with large component libraries. <p>You can generate a description for a single component, or generate descriptions for many components at the same time.</p> <p>(Documentation link to follow.)<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | October 28, 2026 |
| **Adobe Brand Visibility integration**<br/>Connect Adobe Brand Visibility with your organization's Adobe Analytics data so you can measure how AI-driven discovery translates into real website engagement and business outcomes.<p>(Documentation link to follow.)</p> | | October 2026 |
| **CX Enterprise Coworker: Analyze Adobe Analytics data in Coworker Chat** <br/>Adobe CX Enterprise Coworker Chat can now perform advanced data analysis that was previously possible only in Analysis Workspace. Coworker Chat accesses data from your Adobe Analytics report suites, allowing you to explore that data and get answers to natural-language prompts.<p>(Documentation link to follow.)</p> | October 2, 2026 | TBD<p>(Originally planned for September 25, 2026)</p> |

### Fixes in Adobe Analytics

**Activity Map**: AN-494609, AN-493182
**Analysis Workspace**: AN-495340, AN-494789, AN-493307, AN-468900
**Classifications**: AN-498043, AN-496619, AN-496468, AN-496217, AN-496133, AN-495567, AN-494651, AN-494345, AN-494312, AN-494261, AN-493645, AN-493507, AN-493336, AN-492869, AN-492812, AN-492751, AN-492750, AN-492741, AN-491032, AN-490802, AN-490796, AN-467849
**Data Feeds and Data Warehouse**: AN-494937, AN-493065, AN-489796, AN-479109
**Migration**: AN-489850, AN-468014
**Exports**: AN-494337, AN-486563
**Report Builder**: AN-496602, AN-494224, AN-493737, AN-493508, AN-493505, AN-492806, AN-468981, AN-454376
**Reporting**: AN-493637, AN-461260
**Report suites**: AN-496773, AN-495227, AN-494981, AN-494372, AN-494370, AN-493629
**Scheduled reports**: AN-491103
**Segmentation**: 
**Other**: AN-496398, AN-494453, AN-492494

### End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Legacy Report Builder** | June 18, 2025 | The legacy Report Builder add-in was retired in June 2026. All users should begin upgrading their legacy workbooks to the [new Report Builder](/help/analyze/report-builder/rb-overview.md). The new Report Builder is available to both Adobe Analytics and Customer Journey Analytics customers. It has [near feature parity](/help/analyze/report-builder/convert-workbooks.md#unsupported) plus many new convenient features and UI enhancements. To facilitate the upgrade process, the new Report Builder includes an easy workbook conversion feature. The new Report Builder is only available as an add-in through the Microsoft Store. Many organizations require an internal approval process before the add-in can be made available to users. Please allow time for this process and begin working with your organization now to ensure enough time to upgrade your workbooks prior to the EOL date. |
| **Adobe Analytics API (version 1.4)** | July 17, 2024 | On **August 31, 2026**, the following Analytics Legacy API services reached their end of life and were shut down, and any integrations built using these services no longer function:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Integrations that use the Adobe Analytics API (version 1.4) must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) for answers to common questions and further guidance.</p> |

## AppMeasurement

For the latest updates on AppMeasurement releases, please refer to [AppMeasurement release notes](https://github.com/adobe/appmeasurement/releases).

## Postponed features

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **Streaming media services: Support schedule data** <br/>You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | October 29, 2025 | TBD<p>(Originally planned for October 29, 2025)</p> |


>[!MORELIKETHIS]
>
>* [Previous release notes for 2026](/help/release-notes/2026.md)
>* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
>* [Streaming media services release notes](https://experienceleague.adobe.com/en/docs/media-analytics/using/release-notes/release-notes)
>* The latest release updates for [Adobe CX Enterprise products](https://business.adobe.com/products/adobe-experience-cloud-products.html)

