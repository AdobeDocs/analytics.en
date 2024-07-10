---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (July 2024)

**Last update**: July 10, 2024

These release notes cover the release period of July 17, 2024 through August 2024. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Web SDK improvements for link tracking** | Several notable improvements are available in the latest version of the Web SDK around link tracking, which directly benefits Activity Map. These new features are available in both the Web SDK JavaScript library and the Web SDK tag extension.<ul><li>Event grouping: When a visitor clicks an internal link, you can choose to group event data on the next page instead of triggering a separate event call for link tracking. This improvement reduces the number of events that the Web SDK uses against your contractual limit.</li><li>Filter click properties: A new callback that replaces `OnBeforeLinkClickSend`. You can use this callback to filter or obfuscate link-related data before sending it to Adobe.</li></ul><p>See [clickCollection](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollection) in the Web SDK user guide for more information.</p> | Open Beta starts July 10, 2024 | TBD |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed the following Classifications issues: AN-347682; AN-348396; AN-348625; AN-348668; AN-348926; AN-348936; AN-349040; AN-349191; AN-349195; AN-349443; AN-349697; AN-349758; AN-349862; AN-350051; AN-350054; AN-350208; AN-350497; AN-350525; AN-351067
* Fixed the following Data Warehouse issues: AN-346862; AN-349409; AN-349926; AN-350629; AN-350996
* Fixed the following Data Feeds issues: AN-346727; AN-348282; AN-348334; AN-348725; AN-348726; AN-348823; AN-349081; AN-349207; AN-349307; AN-349539; AN-349710; AN-349729; AN-349742; AN-349878; AN-349943; AN-350527; 
* Fixed the following Data Sources issue: AN-350038
* Fixed the following Analysis Workspace issues: AN-342953; AN-346346; AN-349590; AN-349717; AN-350057; AN-350697; AN-350904
* Fixed the following Report Builder issues: AN-348903; AN-350691
* Fixed the following A4T issues: AN-347690; AN-350853

### Other Analytics fixes

AN-346470; AN-346850; AN-347227; AN-348145; AN-348564; AN-349001; AN-349008; AN-349211; AN-349719; AN-350523;

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **13-month expiration of saved `cust_visids`**  | May 22, 2024 | An upcoming release of the Analytics Hit processing engine, **targeted for July 2024**, will start enforcing a 13-month expiration of saved `cust_visids`. If the report suite has "Enable Visitor Stitching" enabled, this setting is used for finding the `cust_visid` for a `visid_high/visid_low value` with no `cust_visid` on the hit. Currently, there is no expiration of the mapping of a `cust_visid` for a `visid_high/visid_low`. With this release, if 13 months or more have passed since `visid_high/visid_low` has had a `cust_visid` on a hit, the mapping expires. | 

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **EOL for Analytics 1.4 API** | July 17, 2024  | On **August 12, 2026**, the following Analytics Legacy API services will reach their end-of-life and will be shut down, and current integrations built using these services will stop working:<ul><li>Adobe Analytics 1.4 API</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Adobe Analytics 1.4 API integrations must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) for answers to common questions and further guidance.</p>  |
| **EOL for non-Campaign customers configuring Triggers API through Adobe I/O** | July 17, 2024 | On **September 1, 2024**, Adobe will sunset the ability to configure the Triggers API through Adobe I/O for customers that do not have both Campaign and Analytics. <p>This affects only Adobe Analytics customers who are not using Adobe Campaign. If you have an active Adobe Analytics account and an Adobe Campaign account, whether you set up Triggers through Campaign or through Adobe I/O, the UI experience remains the same.</p><p>Any standard Triggers you set up through the Campaign UI remain the same.</p> |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.26.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2024](/help/release-notes/2024.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Streaming Media Collection Add-on release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
