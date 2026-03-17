---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (March 2026)

**Last update**: March 11, 2026

These release notes cover the March 2026 release period. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes are updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature and description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ---- |
| **Sort tables by multiple columns** <br/>You can now sort the data of a freeform table by multiple columns in Analysis Workspace, whether they are dimensions or metrics.<p>When you sort data for multiple columns, data is sorted according to the priority you assign to each column. Priority numbering is displayed next to the sort icon.</p><p>For more information, see [Filter and sort freeform tables](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | January 28, 2026 | March 4, 2026 <p>(Originally planned for February 18, 2026)</p> |
| **Report Builder: Administrator visibility to all scheduled workbooks**<br/>The Report Builder Excel Add-in includes a new filter option that allows administrators to see all scheduled workbooks for a given org, regardless of who scheduled them. This filter option is available only for Analytics administrators. It is available on both the Workbook tab and the Legacy tab when viewing scheduled workbooks.<p>The ability to view all scheduled workbooks is especially useful when migrating workbooks across distributed teams, because it allows administrators to easily locate all legacy workbooks prior to migrating them.</p><p>Previously, administrators could see only the workbooks they scheduled, not those scheduled by other users.</p><p>For more information, see [Managed scheduled workbooks](/help/analyze/report-builder/manage-schedules-reportbuilder.md).</p> | | March 10, 2026 |
| **Update to the Approximate Count Distinct function**<br/>The HLL probabilistic algorithm used in the Approximate Count Distinct function will soon be updated. The resulting output for numbers utilizing this function might change slightly from historical numbers, as follows:</p><ul><li>When counting very small amounts of unique values, the results will be improved to use exact counts rather than using estimates.</li><li>When counting anything larger, count estimates will retain the same accuracy as prior to this update (estimates are accurate within 5 percent of the exact number, 95 percent of the time).</li></ul><p>For more information about the Approximate Count Distinct function, see [Approximate Count Distinct](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct) in [Advanced functions](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)</p> | | March 10, 2026 |
| **Hands-on tutorial for Analysis Workspace**<br/>A new hands-on tutorial is now available to guide new users through the basics of using panels, visualizations, and components in Analysis Workspace. <p>For more information, see [Adobe Analytics landing page](/help/analyze/landing.md).</p> | | March 18, 2026 |
| **Apply a breakdown to a panel**<br/>You can now apply a breakdown to a panel. When applying a breakdown at the panel level, the breakdown is applied to all columns in all freeform tables within the panel.  | March 2026 | May 2026 |
| **Streaming media services: Support schedule data** <br/>You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership.<p>The following are examples of live content that are supported with schedule data upload:</p><ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul><p>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments.</p><p>These capabilities are available regardless of how you implemented Streaming Media Collection.</p><p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments.</p><p>For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)</p>| October 29, 2025 | First half of 2026<p>(Originally planned to release on October 29, 2025)</p>|

## Fixes in Adobe Analytics

**Activity Map**: 
**Analysis Workspace**: AN-440336, AN-440216, AN-440121, AN-438445, AN-438216, AN-437856, AN-437776, AN-437765, AN-437365, AN-432793, AN-432094, AN-431557, AN-431200, AN-429621, AN-429424, AN-427973, AN-426089, AN-425883, AN-424359
**Classifications**: AN-440143, AN-439891, AN-439844, AN-438994, AN-438057, AN-438052, AN-437986, AN-437896, AN-435387, AN-435335, AN-435150, AN-433050, AN-432062, AN-431873, AN-429642
**Data Feeds and Data Warehouse**: AN-439441, AN-437086, AN-433064, AN-432121, AN-431755, AN-428239, AN-427049, AN-425036, AN-424972, AN-423509, AN-335417, AN-283958, AN-256948
**Migration**: 
**Exports**: AN-432030 
**Report Builder**: AN-437895, AN-437083, AN-434288, AN-434209, AN-433224, AN-430622
**Reporting**: AN-434545, AN-431206, AN-428043
**Scheduled reports**: 
**Segmentation**: 
**Other**: AN-440076, AN-434783, AN-434542, AN-434233, AN-433368, AN-432138, AN-431322, AN-431012, AN-429067, AN-423285


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
