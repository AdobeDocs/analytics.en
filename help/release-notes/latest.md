---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (March 2025 release)

**Last update**: April 4, 2025

These release notes cover the release period of March 5 through May 2025. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analytics inventory** | Analytics Inventory provides a comprehensive overview of your Adobe Analytics environment, including the number of projects and components, report suites, users, and more. By automating the inventory process, you can quickly understand the effort needed to switch from Adobe Analytics to Customer Journey Analytics. This will make the transition easier and faster. [Learn more](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/analytics-inventory)|  | March 26, 2025 |
| **Update to Analytics context data field `a.locale`** | This update changes how the Analytics context data field `a.locale` is set when collecting data via Experience Edge. When data is sent to Adobe Analytics using Experience Edge, Analytics fields are populated based on a mapping of XDM fields. The mapping for `c.a.locale` references a non-standard XDM field, `xdm.environment.language`. This field will be updated to reference the correct field, `xdm.environment._dc.language`.<p>The mapping will continue to reference `xdm.environment.language` for backwards compatibility. For continuity, if both fields are set, `xdm.environment.language` takes precedence. You can view the full list of mappings from XDM to standard Analytics fields [here](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/xdm-var-mapping).  | | March 5, 2025 |
| **Customer Journey Analytics upgrade guide** | Lets you generate a step-by-step guide for upgrading from Adobe Analytics to Customer Journey Analytics. This guide is tailored to your organization and takes into consideration your current Adobe Analytics environment, your intended uses for Customer Journey Analytics, and any time-saving tradeoffs your organization wants to make.<p>To start generating your custom guide, log in to [!DNL Customer Journey Analytics], then select **[!UICONTROL Upgrade to Customer Journey Analytics]** on the **[!UICONTROL Workspace]** tab.<p>[Learn more](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |  | March 11, 2025 |
| **Data Warehouse-only dimensions** | Starting in May 2025, Adobe will begin setting certain dimensions (custom variables such as eVars and props) as 'Data Warehouse-only". This will apply to dimensions that exhibit the following characteristics:<ul><li> Over a period of multiple months, the variable hits the low traffic limit within the first few days of the month.</li><li>> 90% of the values passed in are seen only once during the month.</li></ul>Examples include dimensions containing timestamps, UUIDs or other data which have extremely high cardinality and where unique new values are passed into for almost every hit (or visit or visitor) throughout the month.These dimensions usually exceed the low-traffic limits very quickly and only a very small portion of the values are reportable in Analysis Workspace. This makes reports utilizing these dimensions confusing, since they do not show useful or accurate information. These dimensions do not follow the purpose of or benefit from the low-traffic functionality, which is intended to provide a way to do reporting on values that become 'popular' after the dimension has exceeded the low-traffic limits during the month. [Learn more](https://experienceleague.adobe.com/en/docs/analytics/technotes/low-traffic.)<p>Dimensions marked as "Data Warehouse-only" will not be available for reporting in Analysis Workspace. However, they will still be available for reporting through Data Warehouse, because low-traffic limits do not apply here.<p>This does not mean that every dimension that has hit the low-traffic limits is a candidate to be marked as "Data Warehouse-only". Most dimensions that hit the low-traffic limits actually meet the intention of low-traffic functionality:<ul><li>Most values passed in are not unique.</li><li>Common values continue to come in after the low-traffic limits have been reached during the month.</li><li>New 'popular' values can still occur.</li></ul>It is only the dimensions where almost all values passed in are new and unique that will be marked as "Data Warehouse-only". Increasing the low-traffic limits is not a solution given the uniqueness of the data being collected in these situations. | | May 2025 |
 

## Fixes in Adobe Analytics

**Activity Map**: AN-361038
**Admin Tools**: AN-362178; AN-369483
**Analytics API 1.4**: AN-369615
**Analysis Workspace**: AN-353491; AN-363403; AN-367230; AN-367313; AN-368582; AN-369821; AN-370227; 
**Classifications**: AN-369848; AN-370196; AN-370226; AN-370437
**Data Feeds**: AN-366162; AN-368906; AN-369066; AN-369087; AN-369225; AN-369798
**Data Governance**: AN-365157
**Data Sources**: AN-367550
**Platform**: AN-363931
**Report Builder**: AN-367460; AN-368975

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| N/A |  |  |

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | January 17, 2025 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **June 30, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL for Adobe Analytics API (version 1.4)** | July 17, 2024  | On **August 12, 2026**, the following Analytics Legacy API services will reach their end of life and will be shut down, and current integrations built using these services will stop working:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Integrations that use the Adobe Analytics API (version 1.4) must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) for answers to common questions and further guidance.</p>  |


## AppMeasurement

For the latest updates on AppMeasurement releases, please refer to [AppMeasurement release notes](https://github.com/adobe/appmeasurement/releases).


## Related resources

* [Previous release notes for 2025](/help/release-notes/2025.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
