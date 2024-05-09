---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (May 2024)

**Last update**: May 9, 2024

These release notes cover the release period of May 14, 2024 through June. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
|**New documentation for upgrading from Adobe Analytics to Customer Journey Analytics** | For organizations upgrading from Adobe Analytics to Customer Journey Analytics, there are multiple upgrade options and many considerations to keep in mind based on an organization's current Adobe Analytics implementation and long-term goals. New documentation resources are now available to help you better understand:<ul><li>The various upgrade paths that exist</li><li>Which upgrade paths are available based on an organization's current Adobe Analytics implementation</li><li>The advantages and disadvantages of each upgrade path</li><li>Step-by-step guidance for each upgrade path</li><li>Considerations for handling historical data</li></ul>[Get started with the upgrade to Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted)| Available now |
| **Analytics Real-time Reporting 2.0 API** | The new Real-time Reporting API 2.0 in Adobe Analytics improves customer integration and provides rapid reporting results. These results can be used programmatically to work with basic, trended, and breakdown reports. [Learn more](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/real-time/) | May 30, 2024 | 
| **Streaming Media: Send web data to Adobe Experience Platform Edge Network with the Web SDK** | You can now use the Adobe Experience Platform Web SDK to send Streaming Media web data to Adobe Experience Platform Edge Network, allowing you to build more personalized campaigns and provide more personalized content, resulting in more tracking data to report on.<p>This enhancement provides a unified collection method for web implementations across all Platform solutions, such as Customer Journey Analytics, RT-CDP, AJO, and Event Forwarding. Previously, the only way to send Streaming Media web data to Edge Network was by using the Media Edge API. [Learn more](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge) | May 31, 2024 |
| **Increase in default low-traffic thresholds**| In **mid April 2024**, Adobe will begin increasing the default report suite low-traffic thresholds as follows: ![low-traffic thresholds](assets/thresholds.png) This will impact only variables which are currently set below the new thresholds. These changes will be made incrementally, and we expect the work to be complete by the **end of May**. As these increases are rolled out, you may notice changes for high-cardinality variables:<ul><li>More dimension values may be available for reporting.</li><li>Segments and calculated metrics may include more data.</li><li>Virtual report suites based on segments may include more data.</li><li>Classification exports may include more data.</li></ul> | Mid April, 2024 | May 31, 2024  |
| **Activity Map to use fewer server calls for Web SDK** | Currently, Activity Map link events are counted as their own events and incur extra cost. This enhancement takes some link events and packages them into the next hit, similar to how events are handled by AppMeasurement. (Documentation to follow) |  | May 31, 2024 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed the following Classifications issues: AN-343186; AN-344711; AN-344856; AN-345094; AN-345179; AN-346265; AN-345288; AN-346339; AN-346560; AN-347572; AN-347768; 
* Fixed the following Data Warehouse issues: AN-346789; AN-347031; AN-347568;
* Fixed the following Data Feeds issues: AN-343616; AN-345831; AN-345988; AN-346124; AN-346232; AN-346972; AN-347680; 
* Fixed the following Data Sources issue: AN-347890; 
* Fixed the following Analysis Workspace issues: AN-321503; AN-343471; AN-345171; AN-345223; AN-345912; AN-346026; AN-346330; AN-346839
* Fixed the following A4T issue: AN-345118; 

### Other Analytics fixes

AN-327749; AN-332949; AN-343171; AN-343708; AN-344034; AN-345559; AN-346023; AN-346230; AN-346330; AN-346469; AN-346606; AN-346750; AN-347026; AN-347110; AN-347439; 

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **13-month expiration of saved `cust_visids`**  | March 20, 2024 | An upcoming release of the Analytics Hit processing engine, targeted for April or May, will start enforcing a 13-month expiration of saved `cust_visids`. If the report suite has "Enable Visitor Stitching" enabled, this setting is used for finding the `cust_visid` for a `visid_high/visid_low value` with no `cust_visid` on the hit. Currently, there is no expiration of the mapping of a `cust_visid` for a `visid_high/visid_low`. With this release, if 13 months or more have passed since `visid_high/visid_low` has had a `cust_visid` on a hit, the mapping expires. | 

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
