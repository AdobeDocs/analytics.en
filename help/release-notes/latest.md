---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (July 2024)

**Last update**: July 17, 2024

These release notes cover the release period of July 17, 2024 through August 2024. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Web SDK improvements for link tracking** | Several notable improvements are available in the latest version of the Web SDK around link tracking, which directly benefits Activity Map. These new features are available in both the Web SDK JavaScript library and the Web SDK tag extension.<ul><li>Event grouping: When a visitor clicks an internal link, you can choose to group event data on the next page instead of triggering a separate event call for link tracking. This improvement reduces the number of events that the Web SDK uses against your contractual limit.</li><li>Filter click properties: A new callback that replaces `OnBeforeLinkClickSend`. You can use this callback to filter or obfuscate link-related data before sending it to Adobe.</li></ul><p>See [clickCollection](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollection) in the Web SDK user guide for more information.</p> | Open Beta started July 10, 2024 | TBD |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed an issue that prevented users from logging in to the Analytics UI (AN-352953)
* Fixed an issue that prevented users from logging in to the Analytics mobile app (AN-352463)
* Fixed an issue that prevented downloading the project as a PDF (AN-352680)
* Fixed an issue where classifications were not being imported (AN-352178)

### Other Analytics fixes

AN-352905; AN-352902; AN-352693; AN-352659; AN-352619; 
AN-352577; AN-352575; AN-352572; AN-352571; AN-352549; AN-352501; AN-352499; AN-352478; AN-352466; AN-352437; AN-352378; AN-352355; AN-352341; AN-352318; AN-352297; AN-352272; AN-352267; AN-352263; AN-352088; AN-352019; AN-352018; AN-351978; AN-351908; AN-351809; AN-351750; AN-351689; AN-351624; AN-351564; AN-351524; AN-351507; AN-351416; AN-351414; AN-351405; AN-351299; AN-351283; AN-351231; AN-350710; AN-349912; AN-349786; AN-348300; AN-348061; AN-347865; AN-347676; AN-347478; AN-343611; AN-343114; AN-334124

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **13-month expiration of saved `cust_visids`**  | May 22, 2024 | An upcoming release of the Analytics Hit processing engine, **targeted for July 2024**, will start enforcing a 13-month expiration of saved `cust_visids`. If the report suite has "Enable Visitor Stitching" enabled, this setting is used for finding the `cust_visid` for a `visid_high/visid_low value` with no `cust_visid` on the hit. Currently, there is no expiration of the mapping of a `cust_visid` for a `visid_high/visid_low`. With this release, if 13 months or more have passed since `visid_high/visid_low` has had a `cust_visid` on a hit, the mapping expires. | 

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
