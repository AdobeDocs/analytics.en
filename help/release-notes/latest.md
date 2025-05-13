---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (May 2025 release)

**Last update**: May 8, 2025

These release notes cover the release period of April xx through June 18, 2025. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace left panel no longer opens and closes on hover** | The left panel in Analysis Workspace is used to add things like components, panels, and visualizations to your project. The option to temporarily open the left panel by hovering over one of the icons on the far left is no longer available. Instead, simply click one of these icons to keep the panel open, then click the same icon to close it. |  | May 29, 2025  |


## Fixes in Adobe Analytics

**Alerts**: AN-378351
**Analysis Workspace**: AN-363521; AN-367366; AN-373575; AN-374238; AN-374295; AN-374382; AN-376938; AN-377176; AN-377467; AN-377942
**Asset transfer**: AN-373381 
**Classifications**: AN-373166; AN-373479; AN-376074; AN-377337; AN-377505
**Components**: AN-314468
**Data feeds**: AN-370241; AN-375267; AN-376940
**Data Sources**: AN-375259
**Data Warehouse**: AN-370415; AN-372090; 
**Platform**: AN-365681; AN-372306; AN-372616; 
**Real-time reporting**: AN-365681
**Report Builder**: AN-371395
**Segmentation**: AN-373576; AN-375858
**Virtual report suites**: AN-377948; AN-377952
**Vista rules**: AN-373292

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **Analysis Workspace left panel no longer opens and closes on hover** | The left panel in Analysis Workspace is used to add things like components, panels, and visualizations to your project. The option to temporarily open the left panel by hovering over one of the icons on the far left is no longer available. Instead, simply click one of these icons to keep the panel open, then click the same icon to close it. |  | May 29, 2025 |


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
