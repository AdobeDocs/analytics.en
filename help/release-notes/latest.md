---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (February 2024)

**Last update**: February 14, 2024

These release notes cover the release period of February 14, 2024 to March 11, 2024. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Activity Map for Web SDK without extra cost** | Currently, Activity Map link events are counted as their own events and incur extra cost. This enhancement takes some link events and packages them into the next hit, similar to how events are handled by AppMeasurement. |  | February 14, 2024 |
| **Increase in default low-traffic thresholds**| In **mid April 2024**, Adobe will begin increasing the default report suite low-traffic thresholds as follows: ![low-traffic thresholds](assets/thresholds.png) This will impact only variables which are currently set below the new thresholds. These changes will be made incrementally, and we expect the work to be complete by the **end of May**. As these increases are rolled out, you may notice changes for high-cardinality variables:<ul><li>More dimension values may be available for reporting.</li><li>Segments and calculated metrics may include more data.</li><li>Virtual report suites based on segments may include more data.</li></ul> | Mid April, 2024 | End of May, 2024 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed the following Classifications issues: AN-319515; AN-337559; AN-338149; AN-338702; AN-338769; AN-338891; AN-339327; AN-339649; AN-339668; AN-339669; AN-339776; AN-339822; AN-340017; AN-340202; AN-340476; 
* Fixed the following Classifications Rule Builder issues: AN-338385; AN-338399; AN-338592; AN-338810; AN-338893; AN-339431; AN-339894; AN-339933; AN-340201; AN-340309; 
* Fixed the following A4T issues: AN-334830; AN-336194; AN-338309; AN-338650; 
* Fixed the following Data Collection issue: AN-339323
* Fixed the following Data Warehouse issues: AN-335542; AN-331425; AN-337215; AN-338445; AN-338643; AN-338651; AN-339461; AN-340066; AN-340207; AN-340460
* Fixed the following Data Feeds issues: AN-335952; AN-338653; AN-339508; AN-339681; AN-340418
* Fixed the following Data Sources issues: AN-338648
* Fixed the following Analysis Workspace issues: AN-326509; AN-336186; AN-336190; AN-336309; AN-337922; AN-338094; AN-338323; AN-338556; AN-339600; AN-340445

### Other Analytics fixes

AN-328239; AN-332908; AN-335449; AN-335517; AN-336075; AN-336100; AN-336128; AN-338088; AN-338270; AN-338393; AN-338494; AN-339326; AN-339742; AN-339883; AN-340419; 

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| Adobe API object member additions | January 17, 2024 | Adobe may add optional request and response members (name/value pairs) to existing API objects at any time and without notice or changes in versioning. Adobe recommends that you refer to the API documentation of any third-party tool you integrate with our APIs so that such additions are ignored in processing, if not understood. If implemented properly, such additions are non-breaking changes for your implementation. Adobe will not remove parameters or add required parameters without first providing standard notification through release notes. |
| `getPageLoadTime` plugin deprecated | January 10, 2024 | This plugin is no longer supported. Its code utilizes the performance.timing method, which (according to MDN) has been [deprecated](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). Work on an updated plugin has started. |

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.25.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2023](/help/release-notes/2023.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
