---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (January 2026 release)

**Last update**: January 8, 2026

These release notes cover the release period of October through early November, 2025. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Classification sets rule builder** | Added rule builder functionality to classification sets. You define rules within the context of a classification set. Rules are applied (when activated) to all report suite and key dimension combinations that are subscribed to the classification set.<p>(Documentation link to follow.)</p> |  | January 30, 2026 |
| **Improved data feeds** | The following improvements are now available for data feeds:<ul><li>Improved user experience.</li><li>New experience for creating and managing column templates.</li><li>You can now choose when to create a column template for re-use in future data feeds. You can also delete, edit, and copy templates.</li><li>Previously, each data feed that was created resulted in a new column template, which resulted in a large number of unused column templates and no way to delete or manage them.</li><li>Add and filter by tags.</li><li>View the history of data feed jobs. (When the request period began, when it started, finished, and so forth.)</li><li>Resend or reprocess data feeds. (From the Job history page)</li><li>Allow late-arriving hits. You can now include data that arrived after the data feed job finished processing data within the set reporting frequency.</li><li>When choosing an end date for a data feed, the end date you choose is included as the last day of the data feed.<br/>Previously, the end date was excluded from the data feed.</li></ul><p>**Note:** With these improvements, the URLs to data feed pages in Adobe Analytics are also being updated. Please update any existing bookmarks to point to the new data feeds pages by April 30, 2026.</p>(Documentation link to follow.)</p> | January 20, 2026 | February 10, 2026 |
| **Sort tables by multiple columns** | You can sort the data of a freeform table by any columns in Analysis Workspace, whether they are dimensions or metrics.<p>When you sort data for multiple columns, data is sorted according to the priority you assign to each column. Priority numbering is displayed next to the sort icon.</p><p>(Documentation link to follow.)<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | January 28, 2026 | February 18, 2026 |
| **Streaming media services: Support schedule data** | You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p>| October 29, 2025 | First half of 2026<p>(Originally planned to release on October 29, 2025)</p>|

## Fixes in Adobe Analytics

**Activity Map**: 
**Analysis Workspace**: AN-399209, AN-397146, AN-394992, AN-390795
**Classifications**: AN-400583, AN-399205, AN-398580, AN-398257, AN-395921, AN-394973
**Data collection**: 
**Data Feeds and Data Warehouse**: AN-400938, AN-399075, AN-398924, AN-398573, AN-396574, AN-393946
**Privacy**: 
**Report Builder**: AN-401127, AN-400618, AN-392971, AN-391692
**Reporting**: 
**Scheduled reports**: 
**Segment comparison**: 
**Other**: AN-396084


## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Livestream processing improvements** | January 8, 2026 | Adobe plans to make improvements and changes to the formatting of LiveStream payloads. These updates provide better parity between LiveStream and other Adobe Analytics features, such as Analysis Workspace. A preview endpoint is available that allows you to test the planned changes. See [LiveStream release notes] for the full list of changes and preview endpoint details. Adobe plans a hard cutover to the updated payload format on April 13, 2026. |
| **Legacy Report Builder** | June 18, 2025 | The legacy Report Builder add-in will be retired in June 2026. All users should begin upgrading their legacy workbooks to the [new Report Builder](/help/analyze/report-builder/rb-overview.md). The new Report Builder is available to both Adobe Analytics and Customer Journey Analytics customers. It has [near feature parity](/help/analyze/report-builder/convert-workbooks.md#unsupported) plus many new convenient features and UI enhancements. To facilitate the upgrade process, the new Report Builder includes an easy workbook conversion feature. The new Report Builder is only available as an add-in through the Microsoft Store. Many organizations require an internal approval process before the add-in can be made available to users. Please allow time for this process and begin working with your organization now to ensure enough time to upgrade your workbooks prior to the EOL date. |
| **Access via legacy domains or via legacy SSO** | April 10, 2025 | Adobe plans to update how users access Adobe Analytics to enhance security and streamline your login experience. As part of this effort, access via legacy domains or via legacy SSO, including `my.omniture.com`, will be permanently discontinued on **January 2, 2026**. After this date, legacy login credentials and legacy SSO will no longer work. All users will be required to log in via `experience.adobe.com` using their Adobe Experience Cloud IDs. If you need assistance with your Experience Cloud ID, please contact your organization's Adobe Analytics administrator or [Adobe Customer Care](https://helpx.adobe.com/contact.html). |
| **Adobe Analytics API (version 1.4)** | July 17, 2024  | On **August 12, 2026**, the following Analytics Legacy API services will reach their end of life and will be shut down, and current integrations built using these services will stop working:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Integrations that use the Adobe Analytics API (version 1.4) must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) for answers to common questions and further guidance.</p>  |


## AppMeasurement

For the latest updates on AppMeasurement releases, please refer to [AppMeasurement release notes](https://github.com/adobe/appmeasurement/releases).


## Related resources

* [Previous release notes for 2025](/help/release-notes/2025.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Streaming media services release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
