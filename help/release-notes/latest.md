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
# Current Adobe Analytics release notes (July 2026)

**Last update**: July 8, 2026

These release notes cover the July 2026 release period. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes are updated several times a month. Please check them regularly. 

## New features or enhancements {#features}

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ---- |
| **Sub-hit analysis** <br/>Sub-hit analysis lets you analyze product data at a level more granular than the hit level. Instead of filtering on entire hits, you can segment on individual products within hits. <p>For example, you can segment on a specific product category without including all other products purchased in the same order.</p><p>For more information, see [Sub-hit analysis](/help/components/segmentation/sub-hit.md).</p> | July 8 | End of July, 2026 |
| **AA 2.0 API search features guide** <br/>Use search features to [return a subset of dimension items in reports](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters).<p>For more information, see [Search features](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters) in the Reports endpoint guide on Adobe Developer.  | | July 1, 2026 |
| **Automating recurring reports with AA APIs** <br/>Set up automatic, recurring Adobe Analytics reports for your data pipeline with fresh metrics on a schedule with the Report API. <p>For more information, see the [Automating recurring Analytics reports endpoint guide](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/recurring) on Adobe Developer.</p> | | July 1, 2026 |
| **New expansion parameters for AA** <br/>Use new Dimension API expansion parameters to retrieve eVar configuration fields for allocation types, expirations, data types, and merchandising. <p>For more information, see the [API Reference](https://developer.adobe.com/analytics-apis/docs/2.0/apis/#operation/dimensions_getDimensions) and [Dimensions endpoint guide](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/) on Adobe Developer.</p> | | July 1, 2026 |

### Fixes in Adobe Analytics

**Activity Map**: 
**Analysis Workspace**: AN-449890, AN-457527, AN-451161, AN-459034, AN-458071, AN-458398
**Classifications**: AN-453318, AN-456739, AN-455828, AN-455270, AN-460272, AN-459367, AN-459239, AN-458418, AN-458417
**Data Feeds and Data Warehouse**: AN-456945, AN-460700
**Migration**: 
**Exports**: 
**Report Builder**: AN-457533, AN-453683
**Reporting**: AN-447692, AN-451259, AN-455713
**Report suites**: 
**Scheduled reports**: AN-450715
**Segmentation**: 
**Other**: AN-453982, AN-455771

### End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Legacy Report Builder** | June 18, 2025 | The legacy Report Builder add-in will be retired in June 2026. All users should begin upgrading their legacy workbooks to the [new Report Builder](/help/analyze/report-builder/rb-overview.md). The new Report Builder is available to both Adobe Analytics and Customer Journey Analytics customers. It has [near feature parity](/help/analyze/report-builder/convert-workbooks.md#unsupported) plus many new convenient features and UI enhancements. To facilitate the upgrade process, the new Report Builder includes an easy workbook conversion feature. The new Report Builder is only available as an add-in through the Microsoft Store. Many organizations require an internal approval process before the add-in can be made available to users. Please allow time for this process and begin working with your organization now to ensure enough time to upgrade your workbooks prior to the EOL date. |
| **Adobe Analytics API (version 1.4)** | July 17, 2024  | On **August 12, 2026**, the following Analytics Legacy API services will reach their end of life and will be shut down, and current integrations built using these services will stop working:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Integrations that use the Adobe Analytics API (version 1.4) must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) for answers to common questions and further guidance.</p>  |

## AppMeasurement

For the latest updates on AppMeasurement releases, please refer to [AppMeasurement release notes](https://github.com/adobe/appmeasurement/releases).

## Postponed features

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| -----------|-----------|-----------|
| **Streaming media services: Support schedule data** <br/>You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data) | October 29, 2025 | TBD<p>(Originally planned for October 29, 2025)</p> |


>[!MORELIKETHIS]
>
>* [Previous release notes for 2026](/help/release-notes/2026.md)
>* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
>* [Streaming media services release notes](https://experienceleague.adobe.com/en/docs/media-analytics/using/release-notes/release-notes)
>* The latest release updates for [Adobe CX Enterprise products](https://business.adobe.com/products/adobe-experience-cloud-products.html)

