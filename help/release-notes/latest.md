---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (October 2025 release)

**Last update**: October 10, 2025

These release notes cover the release period of September through early October, 2025. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Filter criteria included in line visualizations and sparklines** | Any filter criteria that you apply to a freeform table can be included in sparklines and connected line visualizations.<p>You can configure sparklines and line visualizations to include filter criteria by selecting the sparkline in the metric column header.</p><p>(Documentation link to follow.) | | October 15, 2025|
| **Analyze AI traffic with a new Referrer Type dimension item** | A new Referrer type dimension item will be available to help analyze traffic that comes from AI tools. <p>This new Referrer type dimension item, called Conversational AI tools, will group together referring domains of major AI tools, allowing you to look at trends for the group as a whole. The initial list of referring domains in this new category includes (but is not limited to):</p><ul><li>chatgpt.com</li><li>claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplexity.ai</li></ul><p>The new dimension item will be available in all Adobe Analytics-related tools including Analysis Workspace, Report Builder, Data Warehouse, Data Feeds, and so forth.</p><p>Consider the following when using this new dimension item:</p><ul><li>It is not always possible to distinguish referrer traffic that came from results provided in "AI mode" in a search engine vs. those that came from click-throughs from traditional search results.</li><li>The new Conversational AI tools dimension item focuses on major providers with the most traffic. A new trend reveals a rising number of impersonator sites with domains similar to major AI tool providers. This is likely due to the ease with which individuals or groups can create their own AI tools and host them on the internet. Because this is a rapidly evolving space, please contact the Adobe support team if you find that a popular site is not included.</li><li>The Referrer type dimension, including the new Conversational AI tools dimension item, is available only for data that is processed by Adobe Analytics. </li></ul><p>(Documentation link to follow.)</p> |   | October 15, 2025 |
| **Streaming media services: Support schedule data** | You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>(Documentation link to follow.)<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p>|  | October 29, 2025 |
| **Streaming media services: Updated XDM fields for collecting Streaming Media data into Adobe Experience Platform** | When collecting streaming media data into Adobe Experience Platform, the XDM field paths shown under the heading of "XDM Field Path" of the Streaming Media parameters documentation should no longer be used. Instead, customers who implemented the Analytics source connector to collect streaming media data into Platform before May 9, 2025 must migrate their existing configurations to the mediaReporting field paths, as shown under the heading of "Reporting XDM Field Path" of the Streaming Media parameters documentation.<p> These field paths are found on the following pages and are marked as "Deprecated": [Audio and video parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Ad parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Chapter parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Player state parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters), and [Quality parameters](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). (No action is required for customers who implement the Analytics source connector after May 9, 2025, and are already using only mediaReporting XDM paths.)</p><p>Data ingestion on the deprecated XDM field paths will continue until the end of October 2025. After that time, deprecated field paths will be fully removed and no longer visible in the Adobe Experience Platform Schema UI, and data will be sent only using the mediaReporting field paths.</p><p>For more information, see [Migrate an Analytics Source Connector implementation to updated XDM streaming media fields](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Please contact your Adobe Consulting Services or Account team for migration support. </p> |  | October 2025 |
| **AA 2.0 API Report suite creation** | Create report suites in Adobe Analytics with the 2.0 APIs. The new POST method replaces the 1.4 report suite API creation in preparation for the upcoming deprecation of the 1.4 APIs. | | October 2025 |

## Fixes in Adobe Analytics

**Activity Map**: 
**Analysis Workspace**: AN-386791, AN-380838, AN-389373, AN-390851, AN-391593, AN-391404, AN-393064, AN-379337
**Classifications**: AN-391364, AN-393014, AN-393882, AN-394346, AN-394333, AN-390201
**Data collection**: AN-388127
**Data Feeds and Data Warehouse**: AN-391243
**Privacy**: 
**Report Builder**: AN-387741, AN-386777, AN-388720, AN-389343
**Reporting**: AN-392863, AN-371871, AN-393640, AN-391334
**Scheduled reports**: AN-391150, AN-390474
**Segment comparison**: 
**Other**: AN-387858, AN-393985, AN-393287


## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Legacy Report Builder** | June 18, 2025 | The legacy Report Builder add-in will be retired in June 2026. All users should begin upgrading their legacy workbooks to the [new Report Builder](/help/analyze/report-builder/rb-overview.md). The new Report Builder is available to both Adobe Analytics and Customer Journey Analytics customers. It has [near feature parity](/help/analyze/report-builder/convert-workbooks.md#unsupported) plus many new convenient features and UI enhancements. To facilitate the upgrade process, the new Report Builder includes an easy workbook conversion feature. The new Report Builder is only available as an add-in through the Microsoft Store. Many organizations require an internal approval process before the add-in can be made available to users. Please allow time for this process and begin working with your organization now to ensure enough time to upgrade your workbooks prior to the EOL date. |
| **Access via legacy domains or via legacy SSO** | April 10, 2025 | Adobe plans to update how users access Adobe Analytics to enhance security and streamline your login experience. As part of this effort, access via legacy domains or via legacy SSO, including `my.omniture.com`, will be permanently discontinued on **January 2, 2026**. After this date, legacy login credentials and legacy SSO will no longer work. All users will be required to log in via `experience.adobe.com` using their Adobe Experience Cloud IDs. If you need assistance with your Experience Cloud ID, please contact your organization's Adobe Analytics administrator or [Adobe Customer Care](https://helpx.adobe.com/contact.html). |
| **Adobe Analytics API (version 1.4)** | July 17, 2024  | On **August 12, 2026**, the following Analytics Legacy API services will reach their end of life and will be shut down, and current integrations built using these services will stop working:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Integrations that use the Adobe Analytics API (version 1.4) must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) for answers to common questions and further guidance.</p>  |


## AppMeasurement

For the latest updates on AppMeasurement releases, please refer to [AppMeasurement release notes](https://github.com/adobe/appmeasurement/releases).


## Related resources

* [Previous release notes for 2025](/help/release-notes/2025.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Streaming media services release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
