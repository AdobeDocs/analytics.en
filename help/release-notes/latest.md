---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (May 2024)

**Last update**: May 7, 2024

These release notes cover the release period of May 14, 2024 through June. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analytics Real-time Reporting 2.0 API** | The new Real-time Reporting API 2.0 in Adobe Analytics improves customer integration, providing rapid reporting results through Adobe I/O, Adobe Gateway, and Analytics Discovery Service. This update eliminates dependencies on the legacy PHP architecture. | May 30, 2024 | 
|**New documentation for upgrading from Adobe Analytics to Customer Journey Analytics** | For organizations upgrading from Adobe Analytics to Customer Journey Analytics, there are multiple upgrade options and many considerations to keep in mind based on an organization's current Adobe Analytics implementation and long-term goals. New documentation resources are now available to help you better understand:<ul><li>The various upgrade paths that exist</li><li>Which upgrade paths are available based on an organization's current Adobe Analytics implementation</li><li>The advantages and disadvantages of each upgrade path</li><li>Step-by-step guidance for each upgrade path</li><li>Considerations for handling historical data</li></ul>[Get started with the upgrade to Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted)| Available now |
| **Increase in default low-traffic thresholds**| In **mid April 2024**, Adobe will begin increasing the default report suite low-traffic thresholds as follows: ![low-traffic thresholds](assets/thresholds.png) This will impact only variables which are currently set below the new thresholds. These changes will be made incrementally, and we expect the work to be complete by the **end of May**. As these increases are rolled out, you may notice changes for high-cardinality variables:<ul><li>More dimension values may be available for reporting.</li><li>Segments and calculated metrics may include more data.</li><li>Virtual report suites based on segments may include more data.</li><li>Classification exports may include more data.</li></ul> | Mid April, 2024 | May 31, 2024  |
| **Activity Map uses fewer server calls for Web SDK** | Currently, Activity Map link events are counted as their own events and incur extra cost. <p>This enhancement takes some link events and packages them into the next hit, similar to how events are handled by AppMeasurement.</p> |  | May 1, 2024 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed the following Classifications issues: AN-347572; AN-347768; 
* Fixed the following Classifications Rule Builder issues: 
* Fixed the following Segmentation issue: 
* Fixed the following Data Warehouse issue: AN-346789; AN-347568;
* Fixed the following Data Feeds issues: AN-346124; AN-346972; AN-347680; 
* Fixed the following Data Sources issue: AN-347890; 
* Fixed the following Analysis Workspace issues: AN-346839
* Fixed the following Analytics Admin issues: 
* Fixed the following A4T issues: 
* Fixed the following Mobile App issue: 

### Other Analytics fixes

AN-347110; AN-347439; 

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **13-month expiration of saved `cust_visids`**  | March 20, 2024 | An upcoming release of the Analytics Hit processing engine, targeted for April or May, will start enforcing a 13-month expiration of saved `cust_visids`. If the report suite has "Enable Visitor Stitching" enabled, this setting is used for finding the `cust_visid` for a `visid_high/visid_low value` with no `cust_visid` on the hit. Currently, there is no expiration of the mapping of a `cust_visid` for a `visid_high/visid_low`. With this release, if 13 months or more have passed since `visid_high/visid_low` has had a `cust_visid` on a hit, the mapping will expire. | 
| **Adobe API object member additions** | January 17, 2024 | Adobe may add optional request and response members (name/value pairs) to existing API objects at any time and without notice or changes in versioning. Adobe recommends that you refer to the API documentation of any third-party tool you integrate with our APIs so that such additions are ignored in processing, if not understood. If implemented properly, such additions are non-breaking changes for your implementation. Adobe will not remove parameters or add required parameters without first providing standard notification through release notes. |

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.26.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2023](/help/release-notes/2023.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
