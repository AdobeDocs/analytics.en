---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (April 2024)

**Last update**: April 11, 2024

These release notes cover the release period of April 17, 2024 through May. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Experience Platform Edge Network - Adoption Acceleration** | Adobe Experience Platform Data Collection now automatically maps many fields from the data object straight to Adobe Analytics. This improved workflow allows your organization to migrate to the Web SDK without worrying about creating or adhering to an XDM schema. See (Data object variable mapping)(https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping) for more information. |  | April 2024 |
| **Use the same cloud accounts for Data Feeds, Data Warehouse, and Classification sets** | Cloud accounts and locations that you create can now be used for exporting data (with Data Feeds and Data Warehouse) and importing data (with Classification sets).<p> **Changes when configuring accounts:** Users can Configure cloud import and export accounts and Configure cloud import and export locations that can be used for any of the following purposes:<ul><li>Importing data with Classification sets</li><li>Exporting data with Data Feeds</li><li>Exporting data with Data Warehouse.</li></ul><p>**Changes when managing accounts**: Users can use the Locations page (under Components > Locations) to view and manage all the accounts and locations that they create, regardless of where they were created. <p>Previously, the Locations page applied only to accounts that were created for importing data with Classification sets.</p> | | April 2024 |
| **Administrators can manage all locations and accounts in their organization** | A new option on the Locations tab (on the Components > Locations page) allows Administrators to view and manage all locations in the organization.<p>A new option on the Location accounts tab (on the Components > Locations page) allows Administrators to view and manage all accounts in the organization.</p> <p>Previously, administrators could view and manage only the locations and accounts that they created.</p> |  | April 2024 |
| **Activity Map uses fewer server calls for Web SDK** | Currently, Activity Map link events are counted as their own events and incur extra cost. <p>This enhancement takes some link events and packages them into the next hit, similar to how events are handled by AppMeasurement.</p> |  | May 1, 2024 |
| **Increase in default low-traffic thresholds**| In **mid April 2024**, Adobe will begin increasing the default report suite low-traffic thresholds as follows: ![low-traffic thresholds](assets/thresholds.png) This will impact only variables which are currently set below the new thresholds. These changes will be made incrementally, and we expect the work to be complete by the **end of May**. As these increases are rolled out, you may notice changes for high-cardinality variables:<ul><li>More dimension values may be available for reporting.</li><li>Segments and calculated metrics may include more data.</li><li>Virtual report suites based on segments may include more data.</li><li>Classification exports may include more data.</li></ul> | Mid April, 2024 | May 31, 2024  |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed the following Classifications issues: AN-343439; AN-343503; AN-343504; AN-343986; AN-344262; AN-344564; AN-345204
* Fixed the following Classifications Rule Builder issues: AN-341488; AN-342501
* Fixed the following Intelligent Alerts issue: AN-343466; 
* Fixed the following Segmentation issue: AN-342313
* Fixed the following Data Warehouse issue: AN-344292
* Fixed the following Data Feeds issues: AN-339545; AN-340092; AN-342124; AN-342862; AN-343737; AN-344035; AN-344329; AN-344703; AN-344721; AN-344940; AN-345180; AN-345196; AN-345225; AN-345236; AN-345326; AN-345631; 
* Fixed the following Data Sources issue: AN-343541
* Fixed the following Analysis Workspace issues: AN-336303; AN-336472; AN-338422; AN-338556; AN-339718; AN-340301; AN-340421; AN-340951; AN-341172; AN-342905; AN-342909; AN-343448; AN-343570; AN-344050; AN-344182; AN-344763; AN-344768; 
* Fixed the following Analytics Admin issues: AN-342519; AN-342523; AN-343623; AN-343882; AN-344237; AN-344829; AN-345235; 
* Fixed the following A4T issue: AN-341619
* Fixed the following Mobile App issue: AN-342010

### Other Analytics fixes

AN-336099; AN-337474; AN-337993; AN-339901; AN-341356; AN-343102; AN-343353; AN-343416; AN-340014; AN-344037; AN-344525; 

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **13-month expiration of saved `cust_visids`**  | March 20, 2024 | An upcoming release of the Analytics Hit processing engine, targeted for April or May, will start enforcing a 13-month expiration of saved `cust_visids`. If the report suite has "Enable Visitor Stitching" enabled, this setting is used for finding the `cust_visid` for a `visid_high/visid_low value` with no `cust_visid` on the hit. Currently, there is no expiration of the mapping of a `cust_visid` for a `visid_high/visid_low`. With this release, if 13 months or more have passed since `visid_high/visid_low` has had a `cust_visid` on a hit, the mapping will expire. | 
| **Adobe API object member additions** | January 17, 2024 | Adobe may add optional request and response members (name/value pairs) to existing API objects at any time and without notice or changes in versioning. Adobe recommends that you refer to the API documentation of any third-party tool you integrate with our APIs so that such additions are ignored in processing, if not understood. If implemented properly, such additions are non-breaking changes for your implementation. Adobe will not remove parameters or add required parameters without first providing standard notification through release notes. |

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **EOL for configuring Triggers API through Adobe I/O** | April 12, 2024 | On September 1, 2024, Adobe will sunset the ability to configure the Triggers API through Adobe I/O. This affects only Adobe Analytics customers who are not using Adobe Campaign.<p>If you have an active Adobe Analytics account and an Adobe Campaign account, and you set up Triggers through Campaign, you will not see an impact. If you have an Adobe Analytics account and an Adobe Campaign account, and you set up Triggers through Adobe I/O, the UI experience will remain the same and any standard Triggers you set up through the Campaign UI will remain the same. However, any custom Adobe I/O projects that you set up outside of the Campaign UI will no longer receive data. |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.26.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2023](/help/release-notes/2023.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
