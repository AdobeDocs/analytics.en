---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (September 2024)

**Last update**: September 5, 2024

These release notes cover the release period of Sept 11, 2024 through early October. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Additional information in the "Used in" column in the calculated metric manager and segment manager** | The "Used in" column in the calculated metric manager and segment manager contains the following new reporting areas:<ul><li>**Report Builder**: Shows the number of calculated metrics or segments that are being used in the Report Builder.</li><li>**Ad hoc components**: Shows the number of ad hoc calculated metrics or ad hoc segments that are being used in projects. These ad hoc calculated metrics and segments (otherwise known as "quick calculated metrics" and "quick segments") can be used only in the project where they were created, so they are reported separately from the "Project" reporting area in the "Used in" column.</li></ul> |  | Sept 11, 2024 |
| **Activity Map v3 extension** | The Activity Map v3 extension is now available. If you have the v2 extension installed, uninstall it before installing the v3 extension. Navigate to **[!UICONTROL Tools]** > **[!UICONTROL Activity Map]** to obtain the latest version of the extension. |  | Sept 3, 2024 |

## Fixes in Adobe Analytics

A4T: AN-355736
Activity Map: AN-353779
Analysis Workspace: AN-348485; AN-349693; AN-357247
Analytics Mobile App: AN-352645
Classifications: AN-355636; AN-355651; AN-355753; AN-356005; AN-356439; AN-356540; AN-356577; AN-356622
Cross-Device Analytics: AN-355138
Data Feeds: AN-356258; AN-357133
Data Warehouse: AN-339292; AN-353807
Export Locations: AN-356912
Privacy API: AN-352420
Report Builder: AN-352555; AN-354316
Scheduled projects: AN-355971
Segmentation: AN-352095;
Target reporting: AN-355748

Other fixes: AN-349698; AN-349880; AN-354860; AN-355355; AN-356289; 

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **13-month expiration of saved `cust_visids`**  | August 20, 2024 | The **August 20, 2024**, release of the Analytics Hit processing engine enforces a 13-month expiration of saved `cust_visids`. If the report suite has "Enable Visitor Stitching" enabled, this setting is used for finding the `cust_visid` for a `visid_high/visid_low value` with no `cust_visid` on the hit. Previously, there was no expiration of the mapping of a `cust_visid` for a `visid_high/visid_low`. With this release, if 13 months or more have passed since `visid_high/visid_low` has had a `cust_visid` on a hit, the mapping expires. |
| **Additional implementation detail XDM fields automatically mapped** | September 11, 2024 | When using the Adobe Experience Platform Edge Network to send data to Adobe Analytics, the XDM fields `xdm.implementationdetails.name` and `xdm.implementationdetails.environment` now automatically map to context data variables `c.a.x.implementationdetails.name` and `c.a.x.implementationdetails.environment`. Please adjust any relevant processing rules to accommodate the availability of these values. |

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **EOL for Adobe Analytics API (version 1.4)** | July 17, 2024  | On **August 12, 2026**, the following Analytics Legacy API services will reach their end-of-life and will be shut down, and current integrations built using these services will stop working:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Integrations that use the Adobe Analytics API (version 1.4) must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) for answers to common questions and further guidance.</p>  |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.26.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2024](/help/release-notes/2024.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Streaming Media Collection Add-on release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
