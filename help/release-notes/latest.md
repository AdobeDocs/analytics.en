---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (February 2025 release)

**Last update**: February 10, 2024

These release notes cover the release period of February 11 through mid March, 2025. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| 
| **Transaction ID retention period** | The Transaction ID retention period of 90 days will be extended to 25 months in February of 2025. The `transactionID` variable uniquely identifies a transaction so the hit can tie to data uploaded through Data Sources. (Documentation links to follow)|  | February 11, 2025 |
| **Data Feeds API reference** | The [reference](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs) for the Data Feeds API is now available. |  |  January 30 |

## Fixes in Adobe Analytics

**A4T**: 
**Activity Map**: 
**Admin Console**: 
**Admin Tools**: 
**Advertising Analytics**: 
**Analysis Workspace**: AN-359974;
**Analytics 1.4 API**: 
**Classifications**: AN-367186; AN-367328;
**Component Migration**: AN-364529; AN-366398; AN-367509; 
**Contribution Analysis**: 
**Data Feeds**: AN-365685; AN-366745; AN-367256; AN-367349
**Data Repair API**: 
**Data Sources**: 
**Data Warehouse**: AN-368178; AN-368331;
**Mobile App**: 
**Overage Alerts**: 
**Platform**: AN-351924; AN-365540; AN-365866; AN-366898; AN-367933
**Report Builder**: AN-366456; AN-366655;
**Reporting Activity Manager**:
**Segmentation**: 
**Virtual Report Suites**: AN-367411
**VISTA rules**: AN-365331

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **Non-Campaign customers will lose access to Triggers** | October 16, 2023 | On January 30, 2025, Adobe Analytics customers that do not have an Adobe Campaign license lost access to the ability to configure and consume [Triggers](https://experienceleague.adobe.com/en/docs/core-services/interface/services/triggers). Customers need to either purchase Campaign, or plan to stop using Triggers, or look into other Adobe tools that offer Triggers capabilities. |

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | January 17, 2025 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **June 30, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL for Adobe Analytics API (version 1.4)** | July 17, 2024  | On **August 12, 2026**, the following Analytics Legacy API services will reach their end of life and will be shut down, and current integrations built using these services will stop working:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Integrations that use the Adobe Analytics API (version 1.4) must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) for answers to common questions and further guidance.</p>  |


## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.26.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2024](/help/release-notes/2024.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
