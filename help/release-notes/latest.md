---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (July 2025 release)

**Last update**: July 10, 2025

These release notes cover the release period of July 7 through August 15, 2025. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Livestream TNT Fields with algorithms** | Livestream is undergoing a refresh to ensure the technology continues to be modern and stable. As part of that refresh, if your TNT field has an algorithm in it, we will begin incorporating the TNT field into Livestream output. However, this includes only the previously supported elements: `campaignId`, `recipeId`, `trafficType`, `actionId`, and `actionName`. The overall TNT schema for Livestream remains unchanged. |   |  July 7,2025 |
| **Updated navigation to Customer Attributes UI**  |  The Customer Attributes user interface is now accessible directly from the app selector in Adobe Experience Cloud. | July 1, 2025 |  TBD |
| **Streaming Media: Support schedule data** | You can now upload scheduled data of past live Streaming Media content to more easily and accurately track viewership. The following are examples of live content that are supported with schedule data upload:<ul><li>FAST (Free Ad Supported TV) platforms</li><li>Local streams</li><li>Live sports</li></ul>Uploading schedule data allows you to track viewership data for individual programs that ran during the time you designate in the upload file. You can even gather viewership data for specific topics or program segments. These capabilities are available regardless of how you implemented Streaming Media Collection.<p>Previously, it was difficult to accurately tie a given session to specific programs when analyzing live content, and it wasn't possible to tie a given session to individual topics or program segments. Learn more |  |  June 25, 2025 |

## Fixes in Adobe Analytics

**A4T**: 
**Advertising Analytics**: 
**Alerts**: 
**Analysis Workspace**: AN-382908; AN-387652; 
**API 1.4**: 
**API 2.0**: 
**Classifications**: AN-382412; AN-383157; AN-384803; AN-385933; AN-387320; AN-387351; AN-387832; AN-387833; AN-387839; AN-387915; 
**Contribution Analysis**: 
**Data feeds**: AN-375172; AN-384369; AN-387859; AN-387952; AN-388155;
**Data Warehouse**: 
**Platform**: AN-382813; AN-386627; AN-386815
**Privacy**: AN-384390
**Processing rules**: 
**Report Builder**: 
**Reporting**: AN-380441
**Scheduled reports**: AN-378280; AN-378331
**Segment comparison**: AN-368766
**Server Calls**: 
**Usage & Access Logs**: 
**Virtual Report Suites**: 


## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Legacy Report Builder** | June 18, 2025 | The legacy Report Builder add-in will be retired in June 2026. All users should begin upgrading their legacy workbooks to the [new Report Builder](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/rb-overview). The new Report Builder is available to both Adobe Analytics and Customer Journey Analytics customers. It has [near feature parity](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks#unsupported) plus many new convenient features and UI enhancements. To facilitate the upgrade process, the new Report Builder includes an easy workbook conversion feature. The new Report Builder is only available as an add-in through the Microsoft Store. Many organizations require an internal approval process before the add-in can be made available to users. Please allow time for this process and begin working with your organization now to ensure enough time to upgrade your workbooks prior to the EOL date. |
| **Access via legacy domains or via legacy SSO** | April 10, 2025 | Adobe plans to update how users access Adobe Analytics to enhance security and streamline your login experience. As part of this effort, access via legacy domains or via legacy SSO, including `my.omniture.com`, will be permanently discontinued on **January 2, 2026**. After this date, legacy login credentials and legacy SSO will no longer work. All users will be required to log in via `experience.adobe.com` using their Adobe Experience Cloud IDs. If you need assistance with your Experience Cloud ID, please contact your organization's Adobe Analytics administrator or [Adobe Customer Care](https://helpx.adobe.com/contact.html). |
| **Adobe Analytics API (version 1.4)** | July 17, 2024  | On **August 12, 2026**, the following Analytics Legacy API services will reach their end of life and will be shut down, and current integrations built using these services will stop working:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Integrations that use the Adobe Analytics API (version 1.4) must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) for answers to common questions and further guidance.</p>  |


## AppMeasurement

For the latest updates on AppMeasurement releases, please refer to [AppMeasurement release notes](https://github.com/adobe/appmeasurement/releases).


## Related resources

* [Previous release notes for 2025](/help/release-notes/2025.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
