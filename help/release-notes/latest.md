---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (October 23, 2024 release)

**Last update**: October 23, 2024

These release notes cover the release period of October 16, 2024 through end of year 2024. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **New Report Builder for Adobe Analytics** | The new Report Builder application brings a major update to Adobe Analytics, including improved performance, streamlined user interface, 2.0 API support and support for Microsoft Excel on Mac, Windows, and web browsers. This application can be used along with the legacy application, but not on the same file. An upgrade feature is provided to upgrade legacy workbooks to the new application. [Learn more](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/report-buider-overview) |  | October 16, 2024 |
| **JSON Export for migrating tags implementation to Web SDK tags**  | This update to the Analytics tags Extension is related to migrating to Web SDK. You can use this update to the Adobe Analytics extension as part of your workflow to recreate your extension configurations with the Web SDK extension. In the Adobe Analytics tags extension, you can view eVars, props and events settings as JSON, which can be exported for editing and included in the Web SDK extension. |  | October 31, 2024 |
| **New information about Request factors in Analysis Workspace Performance** | A new "Request factors" section is now available when analyzing performance in Analysis Workspace. To learn more about how requests are processed and the various factors that influence processing times, see "Request factors" in [Optimize Analysis Workspace performance](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance). |  | October 1, 2024 |

## Fixes in Adobe Analytics
 
Analysis Workspace: AN-356287; AN-358435; AN-359456; AN-359826; AN-360215
Admin Tools: AN-342485; AN-347931; AN-348704; AN-357723; AN-358453; AN-358717; AN-359548; AN-360136
Classifications: AN-359025; AN-359283; AN-359368; AN-359710; AN-359752; AN-359759; AN-359799; AN-359887; AN-360543; AN-360566; AN-360612; AN-360741; AN-360942; AN-360952
Cross-Device Analytics: AN-359210
Customer Attributes: AN-357897
Data Collection: AN-351131; AN-351309; AN-355678; AN-359856
Data Feeds: AN-359699
Data Repair API: AN-360256
Data Sources: AN-359290
Data Warehouse: AN-359820
Overage Alerts: AN-358132

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **Non-Campaign customers will lose access to Triggers** | October 16, 2023 | On January 30, 2025, Adobe Analytics customers that do not have an Adobe Campaign license will lose access to the ability to configure and consume Triggers. Customers need to either purchase Campaign, or plan to stop using Triggers, or look into other Adobe tools that offer Triggers capabilities. |
| **Additional implementation detail XDM fields automatically mapped** | September 11, 2024 | When using the Adobe Experience Platform Edge Network to send data to Adobe Analytics, the XDM fields `xdm.implementationdetails.name` and `xdm.implementationdetails.environment` now always map to context data variables `c.a.x.implementationdetails.name` and `c.a.x.implementationdetails.environment`. Previously, some scenarios prevented these values from populating. Please adjust any relevant processing rules to accommodate the availability of these values. |

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **EOL for Adobe Analytics API (version 1.4)** | July 17, 2024  | On **August 12, 2026**, the following Analytics Legacy API services will reach their end of life and will be shut down, and current integrations built using these services will stop working:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Integrations that use the Adobe Analytics API (version 1.4) must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) for answers to common questions and further guidance.</p>  |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |


## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.26.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2024](/help/release-notes/2024.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Streaming Media Collection Add-on release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
