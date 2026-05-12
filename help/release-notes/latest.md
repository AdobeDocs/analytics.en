---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8
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
# Current Adobe Analytics release notes (April 2026)

**Last update**: April 22, 2026

These release notes cover the April 2026 release period. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes are updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ---- |
| **MCP servers for Adobe Analytics** <br/>The Analytics MCP (Model Context Protocol) servers allow you to connect a supported MCP client to Adobe Analytics. Once connected, your MCP client can invoke product-specific tools to retrieve data, run queries, or perform supported operations as part of an LLM or agentic workflow. For more information, see [Analytics MCP servers](https://developer.adobe.com/analytics-mcp/docs/).<p>If you used these MCP servers during the beta period, please note that there are different URLs between beta and production endpoints. Ensure that any agentic workflows created during the beta period are updated to use the production endpoints before May 31.</p> | | May 5, 2026 |
| **Streaming media services: Support schedule data** <br/>You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p>| October 29, 2025 | First half of 2026<p>(Originally planned to release on October 29, 2025)</p>|
| **Additional API date range formatting**<br/>Two new formats are now supported for specifying date ranges in Analytics 2.0 API report requests. This includes a date formula and a mixed format. [Learn more](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#date-range-field--supported-formats) | | March 2026 |
| **Optional dimension in API report requests**<br/>A dimension object is not required in Report API requests. If no dimension is specified, the response shows data for a Totals report. [Learn more](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#using-dimension-in-report-payload-requests) | | March 2026 |
| **Date-trended advanced API report**<br/>New Adobe Analytics 2.0 API Date-trended Advanced Report Guide. Create advanced date-trended API reports using date range comparisons and segments. [Learn more](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced/) | | March 2026 |

## Fixes in Adobe Analytics

**Activity Map**: 
**Analysis Workspace**: AN-442813, AN-442410, AN-441943, AN-441717, AN-434855, AN-431409, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Classifications**: AN-443453, AN-443275, AN-443148, AN-442906, AN-442232, AN-442207, AN-442148, AN-442133, AN-441937, AN-441901, AN-441807, AN-441671, AN-441333, AN-441302, AN-441149, AN-441132, AN-441085, AN-441048, AN-440846, AN-440727, AN-440716, AN-440511, AN-440496, AN-432100
**Data Feeds and Data Warehouse**: AN-442211, AN-441719, AN-441183, AN-441011, AN-440625, AN-438953
**Migration**: AN-442467, AN-440380, AN-440357
**Exports**: 
**Report Builder**: AN-441136, AN-438147, AN-425150
**Reporting**: AN-441506, AN-440919, AN-440545, AN-440300
**Report suites**: AN-439429, AN-439423, AN-430988
**Scheduled reports**: 
**Segmentation**: 
**Other**: AN-423359, AN-406242, AN-397985


## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Livestream processing improvements** | January 14, 2026 | Adobe plans to make improvements and changes to the formatting of LiveStream payloads. These updates provide better parity between LiveStream and other Adobe Analytics features, such as Analysis Workspace. A preview endpoint is available that allows you to test the planned changes. See [LiveStream release notes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) for the full list of changes and preview endpoint details. Adobe plans a hard cutover to the updated payload format on April 13, 2026. |
| **TLS 1.2 cipher suites removal** | February 11, 2026 | Notice to admins: Adobe plans to remove support for the following TLS 1.2 cipher suites from Adobe data collection servers on May 27, 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>No customer action is required for most implementations. This change primarily affects Analytics data sent from legacy native applications that use outdated TLS libraries, and a small number of web visitors on obsolete browsers or operating systems. Removing support for these cipher suites enhances security and aligns Adobe with modern encryption standards. Less than 0.1% of data collection traffic currently relies on these cipher suites.</p> |
| **Legacy Report Builder** | June 18, 2025 | The legacy Report Builder add-in will be retired in June 2026. All users should begin upgrading their legacy workbooks to the [new Report Builder](/help/analyze/report-builder/rb-overview.md). The new Report Builder is available to both Adobe Analytics and Customer Journey Analytics customers. It has [near feature parity](/help/analyze/report-builder/convert-workbooks.md#unsupported) plus many new convenient features and UI enhancements. To facilitate the upgrade process, the new Report Builder includes an easy workbook conversion feature. The new Report Builder is only available as an add-in through the Microsoft Store. Many organizations require an internal approval process before the add-in can be made available to users. Please allow time for this process and begin working with your organization now to ensure enough time to upgrade your workbooks prior to the EOL date. |
| **Access via legacy domains or via legacy SSO** | April 10, 2025 | Adobe plans to update how users access Adobe Analytics to enhance security and streamline your login experience. As part of this effort, access via legacy domains or via legacy SSO, including `my.omniture.com`, will be permanently discontinued on **January 2, 2026**. After this date, legacy login credentials and legacy SSO will no longer work. All users will be required to log in via `experience.adobe.com` using their Adobe Experience Cloud IDs. If you need assistance with your Experience Cloud ID, please contact your organization's Adobe Analytics administrator or [Adobe Customer Care](https://helpx.adobe.com/contact.html). |
| **Adobe Analytics API (version 1.4)** | July 17, 2024  | On **August 12, 2026**, the following Analytics Legacy API services will reach their end of life and will be shut down, and current integrations built using these services will stop working:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Integrations that use the Adobe Analytics API (version 1.4) must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) for answers to common questions and further guidance.</p>  |


## AppMeasurement

For the latest updates on AppMeasurement releases, please refer to [AppMeasurement release notes](https://github.com/adobe/appmeasurement/releases).


## Related resources

* [Previous release notes for 2025](/help/release-notes/2025.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Streaming media services release notes](https://experienceleague.adobe.com/en/docs/media-analytics/using/release-notes/release-notes)
* The latest release updates for [Adobe CX Enterprise products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
