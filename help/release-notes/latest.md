---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (April 2025 release)

**Last update**: April 16, 2025

These release notes cover the release period of March 26 through May 2025. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analytics inventory** | Analytics Inventory provides a comprehensive overview of your Adobe Analytics environment, including the number of projects and components, report suites, users, and more. By automating the inventory process, you can quickly understand the effort needed to switch from Adobe Analytics to Customer Journey Analytics. This will make the transition easier and faster. [Learn more](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/analytics-inventory)|  | March 26, 2025 |
| **Data Warehouse-only dimensions** | Based on customer feedback, we have decided to re-evaluate. We will not release the automatic Data Warehouse-only dimensions feature as previously announced. | | TBD |

## Fixes in Adobe Analytics

**A4T**: AN-370625; AN-371279; AN-371351
**Admin Tools**: AN-365072; AN-371303
**Analysis Workspace**: AN-363831; AN-369554
**Classifications**: AN-370519; AN-370727; AN-370827; AN-370941; AN-370995; AN-371377; AN-371597; AN-371868; AN-371869; AN-372510; AN-372650; AN-373164; AN-373300; AN-373308; AN-373592
**Data collection**: AN-371877
**Data feeds**: AN-368676; AN-370225; AN-370514; AN-370521; AN-370687; AN-370761; AN-370911; AN-371047; AN-371542; AN-371627; AN-371746; AN-372708; AN-373068; AN-373179
**Data Warehouse**: AN-366649; AN-369817; AN-370705; AN-371127; AN-371995; AN-372596; AN-372940
**Marketing Channels**: AN-372308
**Mobile app**: AN-370287; AN-371335; AN-371374
**Platform**: AN-369510; AN-370435; AN-372150
**Report Builder**: AN-369830; AN-371395; AN-372983

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| N/A |  |  |

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Access via legacy domains or via legacy SSO** | April 10, 2025 | Adobe plans to update how users access Adobe Analytics to enhance security and streamline your login experience. As part of this effort, access via legacy domains or via legacy SSO, including `my.omniture.com`, will be permanently discontinued on **January 2, 2026**. After this date, legacy login credentials and legacy SSO will no longer work. All users will be required to log in via `experience.adobe.com` using their Adobe Experience Cloud IDs. If you need assistance with your Experience Cloud ID, please contact your organization's Adobe Analytics administrator or [Adobe Customer Care](https://helpx.adobe.com/contact.html). |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | January 17, 2025 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **June 30, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL for Adobe Analytics API (version 1.4)** | July 17, 2024  | On **August 12, 2026**, the following Analytics Legacy API services will reach their end of life and will be shut down, and current integrations built using these services will stop working:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Integrations that use the Adobe Analytics API (version 1.4) must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) for answers to common questions and further guidance.</p>  |


## AppMeasurement

For the latest updates on AppMeasurement releases, please refer to [AppMeasurement release notes](https://github.com/adobe/appmeasurement/releases).


## Related resources

* [Previous release notes for 2025](/help/release-notes/2025.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
