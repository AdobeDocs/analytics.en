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
# Current Adobe Analytics release notes (August 2026)

**Last update**: August 5, 2026

These release notes cover the August 2026 release period. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes are updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ---- |
| **Activity Map extension: UI refresh** <br/>The Activity Map overlay extension has an updated look and feel, along with underlying improvements that support upcoming enhancements.<p>For information about the Activity Map overlay extension, see [Activity Map extension interface](/help/analyze/activity-map/overlay/overview.md).</p> | | August 5, 2026<p>(Originally planned for end of July)</p> |
| **Journey canvas enhancements**<br>The following Journey canvas enhancements are now available:<ul><li>Compare the journey to a prior time frame. Compare the current journey to the journey 4 weeks prior, 2 quarters prior, 1 year prior, or to a custom date range.</li><li>For a selected node, show the top dimension items that come after the selected node at any point in the journey. Use this when the selected node is the key event in your analysis and you want to see what people do at any point afterward.<p>Previously, only the top immediate nodes could be shown before or after the selected node. </p></li><li>Change the shape and style of arrows between nodes. Drag arrows between nodes to change the shape (curvature) of the arrow, and right-click an arrow to change its style to any of the following: solid, dashed, dotted, dashed-dot, or animated.</li></ul><p></p>For more information, see [Configure a Journey canvas visualization](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md). | | August 18, 2026 |
| **Limit segments to the reporting date range**<br/>Data in a Workspace report can extend beyond the reporting date range when a segment includes date range components.<p>A new option is now available that allows you to limit results to the reporting date range regardless of any date components included in the segment. <p>This option is available when creating or modifying a segment whose top-level container is Visitor.</p><p>For more information, see [Build segments](/help/components/segmentation/segmentation-workflow/seg-build.md#components).</p> | August 26, 2026 | September 9, 2026 |
| **Analytics API marketing channels reference**<br/>Use the Adobe Analytics 2.0 API marketing channels reference to retrieve Analytics marketing channels information. See the [Analytics API marketing channels reference](https://developer.adobe.com/analytics-apis/docs/2.0/apis/marketing-channels). | | August 1, 2026 |
| **Analytics API marketing channels endpoint guide**<br/>The Adobe Analytics 2.0 API marketing channels endpoint guide provides instructions and examples for using the endpoint. See the [Analytics API marketing channels endpoint guide](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/marketing-channels). | | August 1, 2026 |
| **Analytics 1.4 API EOL customer FAQ**<br/>The Analytics 1.4 API EOL customer FAQ provides information on recent 2.0 API development to assist customers leaving 1.4 APIs. | | August 10, 2026 |

### Fixes in Adobe Analytics

**Activity Map**: AN-404862
**Analysis Workspace**: AN-466867, AN-465995, AN-465315, AN-465313, AN-464375, AN-463634, AN-463248, AN-463175, AN-463049, AN-462347, AN-462124, AN-461922, AN-458398, AN-457849, AN-455002, AN-453357, AN-456863, AN-459816, AN-459034, AN-460774, AN-460671, AN-457760, AN-443594
**Classifications**: AN-467138, AN-467118, AN-467069, AN-466054, AN-465987, AN-465636, AN-465380, AN-464650, AN-464286, AN-463688, AN-462413, AN-462252, AN-462141, AN-462063, AN-462005, AN-461862, AN-461806, AN-461777, AN-461158, AN-460954, AN-460905, AN-460850, AN-460803, AN-460272, AN-460023, AN-459814, AN-459367, AN-459328, AN-459300, AN-459279, AN-459006, AN-458417, AN-458403, AN-457829, AN-457400, AN-454408, AN-449670, AN-460956, AN-459269, AN-458789, AN-461778, AN-461191, AN-460996, AN-460506, AN-459988, AN-459854, AN-458994, AN-457561, AN-457055, AN-454224, AN-454172, AN-459473, AN-459277, AN-459026, AN-455270
**Data Feeds and Data Warehouse**: AN-465273, AN-464245, AN-462435, AN-461000, AN-460700, AN-459225, AN-459192
**Migration**: AN-458185, AN-454285, AN-459239
**Exports**: 
**Report Builder**: AN-465346, AN-464768, AN-464580, AN-464301, AN-463048, AN-462800, AN-457042, AN-461033, AN-459042, AN-454250, AN-451735, AN-450776, AN-450200, AN-451665
**Reporting**: AN-467107, AN-459010, AN-455619, AN-459530, AN-454103
**Report suites**: AN-464246, AN-463756, AN-462101
**Scheduled reports**: AN-455009, AN-460037, AN-462093
**Segmentation**: AN-459002, AN-457730, AN-457146
**Other**: AN-467386, AN-466935, AN-462116, AN-458836, AN-451292, AN-454160, AN-458354, AN-455771, AN-426869, AN-437975

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
| **Streaming media services: Support schedule data** <br/>You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data). | October 29, 2025 | TBD<p>(Originally planned for October 29, 2025)</p> |


>[!MORELIKETHIS]
>
>* [Previous release notes for 2026](/help/release-notes/2026.md)
>* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
>* [Streaming media services release notes](https://experienceleague.adobe.com/en/docs/media-analytics/using/release-notes/release-notes)
>* The latest release updates for [Adobe CX Enterprise products](https://business.adobe.com/products/adobe-experience-cloud-products.html)

