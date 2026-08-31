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
# Current Adobe Analytics release notes (September 2026)

**Last update**: September 1, 2026

These release notes cover the September 2026 release period. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes are updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ---- |
| **Limit segments to the reporting date range**<br/>Data in a Workspace report can extend beyond the reporting date range when a segment includes date range components.<p>A new option is now available that allows you to limit results to the reporting date range regardless of any date components included in the segment. <p>This option is available when creating or modifying a segment whose top-level container is Visitor.</p><p>For more information, see [Build segments](/help/components/segmentation/segmentation-workflow/seg-build.md#components).</p> | August 26, 2026 | September 9, 2026 |
| **Bot detection updates**<br/>When using Edge Data Collection with the Web SDK, the following bot detection updates are available:<ul><li>You can now create bot detection rules to identify exceptions in traffic that would otherwise be treated as bot-generated. Existing and future rules will continue to default to marking matching traffic as bot-generated.</li><li>Custom bot rules now run before IAB bot detection rules. This change does not affect bot scores, but the bot rule names associated with an event may change.</li></ul><p>Note: This update applies only to Edge Data Collection implementations that use the Web SDK. It does not apply to older libraries such as AppMeasurement.</p></p><p>(Documentation link to follow.)</p> | | Early September 2026 |


### Fixes in Adobe Analytics

**Activity Map**: AN-488579, AN-487247
**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373
**Classifications**: AN-490825, AN-490802, AN-490549, AN-490472, AN-487782, AN-487286, AN-486531, AN-478859, AN-469929, AN-469033, AN-468944, AN-468827, AN-468592, AN-468326, AN-467115, AN-466995, AN-465636, AN-465616, AN-465380, AN-464911, AN-464338, AN-463677, AN-462729, AN-462577, AN-461040, AN-459316
**Data Feeds and Data Warehouse**: AN-487624, AN-487287, AN-479923, AN-479166, AN-479109, AN-468483
**Migration**: 
**Exports**: AN-467131
**Report Builder**: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695
**Reporting**: AN-468621, AN-465383, AN-463924
**Report suites**: AN-468484, AN-468460, AN-465385
**Scheduled reports**: 
**Segmentation**: AN-486561
**Other**: AN-488549, AN-467426, AN-465265, AN-464645, AN-459714, AN-459323, AN-454514

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

