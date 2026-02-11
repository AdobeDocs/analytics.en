---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (February 2026)

**Last update**: February 11, 2026

These release notes cover the February 2026 release period. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes are updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ---- |
| **Improved data feeds** <p>The following improvements are now available for data feeds:</p><ul><li>Improved user experience.</li><li>New experience for creating and managing column templates.</li><li>You can now choose when to create a column template for reuse in future data feeds. You can also delete, edit, and copy templates.<br/>Previously, each data feed that was created resulted in a new column template, which resulted in a large number of unused column templates and no way to delete or manage them.</li><li>Add and filter by tags.</li><li>View the history of data feed jobs. (When the request period began, when it started, finished, and so forth.)</li><li>Resend or reprocess data feeds. (From the Job history page)</li><li>Allow late-arriving hits. You can now include data that arrived after the data feed job finished processing data within the set reporting frequency.</li><li>When choosing an end date for a data feed, the end date you choose is included as the last day of the data feed.<br/>Previously, the end date was excluded from the data feed.</li><li>A 15-minute export frequency is now possible, but is not available by default. For this option to become available in your environment, you must first contact Adobe Customer Care and request that your report suite is configured to support 15-minute exports.</li></ul><p>**Note:** With these improvements, the URLs to data feed pages in Adobe Analytics are also being updated. Please update any existing bookmarks to point to the new data feeds pages by April 30, 2026.</p><p>For more information, see [Create a data feed](/help/export/analytics-data-feed/create-feed.md) and [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).</p> | January 20, 2026 | February 24, 2026<p>(Originally planned to release on February 10, 2026)</p> |
| **Sort tables by multiple columns** <p>You can now sort the data of a freeform table by multiple columns in Analysis Workspace, whether they are dimensions or metrics.</p><p>When you sort data for multiple columns, data is sorted according to the priority you assign to each column. Priority numbering is displayed next to the sort icon.</p><p>For more information, see [Filter and sort freeform tables](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | January 28, 2026 | February 18, 2026 |
| **Update to the Approximate Count Distinct function**<p>The HLL probabilistic algorithm used in the Approximate Count Distinct function will soon be updated. The resulting output for numbers utilizing this function might change slightly from historical numbers, as follows:</p><ul><li>When counting very small amounts of unique values, the results will be improved to use exact counts rather than using estimates.</li><li>When counting anything larger, count estimates will retain the same accuracy as prior to this update (estimates are accurate within 5 percent of the exact number, 95 percent of the time).</li></ul><p>For more information about the Approximate Count Distinct function, see [Approximate Count Distinct](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct) in [Advanced functions](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)</p> |  | March 2026 |
| **Streaming media services: Support schedule data** <p>You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.</p><p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p>| October 29, 2025 | First half of 2026<p>(Originally planned to release on October 29, 2025)</p>|
| **New Adobe Analytics 2.0 Report Suites API Guide** <p>Create, retrieve, update, and delete report suite APIs. For more information, see the [Adobe Analytics 2.0 Report Suite API reference guide](https://developer.adobe.com/analytics-apis/docs/2.0/apis/report-suites/) and the [Adobe Analytics 2.0 Report Suite API endpoint guide](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/report-suites/).</p> | | Available now |
| **New Adobe Analytics 2.0 API Anomaly Detection Report Guide** <p>Create an automated API Anomaly Detection report. For more information, see the [Anomaly Detection API Report endpoint guide](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/anomaly/).</p> | | Available now |
| **New Adobe Analytics 2.0 API Basic Date Trended Report Guide** <p>Create an automated API Basic Date Trended KPI Report  For more information, see [Anomaly Detection API Report endpoint guide](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/kpi/).</p> | | Available now |

## Fixes in Adobe Analytics

**Activity Map**: 
**Analysis Workspace**: AN-424997, AN-424194, AN-425515, AN-423174, AN-425207, AN-428834, AN-306540, AN-426014, AN-427801
**Classifications**: AN-422723, AN-424467, AN-423724, AN-424003, AN-425217, AN-396062, AN-422744, AN-425456, AN-425271, AN-425655, AN-424894, AN-429236
**Data Feeds and Data Warehouse**: AN-427082, AN-405154, AN-406512, AN-423594, AN-425283, AN-425208, AN-422510, AN-421189, AN-428986, AN-426724, AN-401525, AN-426884, AN-425146
**Migration**: AN-421192, AN-423443
**Privacy**: 
**Report Builder**: AN-391415, AN-425125
**Reporting**: AN-422123, AN-425817, AN-421097, AN-422249, AN-403446, AN-424727, AN-426791, AN-427985
**Scheduled reports**: AN-425484, AN-425137
**Segmentation**: AN-428905, AN-428232
**Other**: AN-425054, AN-420190, AN-422248


## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Livestream processing improvements** | January 14, 2026 | Adobe plans to make improvements and changes to the formatting of LiveStream payloads. These updates provide better parity between LiveStream and other Adobe Analytics features, such as Analysis Workspace. A preview endpoint is available that allows you to test the planned changes. See [LiveStream release notes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) for the full list of changes and preview endpoint details. Adobe plans a hard cutover to the updated payload format on April 13, 2026. |
| **TLS 1.2 cipher suites removal** | February 11, 2026 | Notice to admins: Adobe plans to remove support for the following TLS 1.2 cipher suites from Adobe data collection servers on May 27, 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>No customer action is required for most implementations. This change primarily affects Analytics data sent from legacy native applications that use outdated TLS libraries, and a small number of web visitors on obsolete browsers or operating systems. Removing support for these cipher suites enhances security and aligns Adobe with modern encryption standards. Less than 0.1% of data collection traffic currently relies on these cipher suites.</p> |
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
