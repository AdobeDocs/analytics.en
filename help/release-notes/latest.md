---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (March 2025 release)

**Last update**: March 6, 2025

These release notes cover the release period of March 5 through mid April, 2025. Adobe Analytics releases operate on a [continuous delivery model](releases.md), which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Update to Analytics context data field `a.locale`** | This update changes how the Analytics context data field `a.locale` is set when collecting data via Experience Edge. When data is sent to Adobe Analytics using Experience Edge, Analytics fields are populated based on a mapping of XDM fields. The mapping for `c.a.locale` references a non-standard XDM field, `xdm.environment.language`. This field will be updated to reference the correct field, `xdm.environment._dc.language`.<p>The mapping will continue to reference `xdm.environment.language` for backwards compatibility. For continuity, if both fields are set, `xdm.environment.language` will take precedence. You can view the full list of mappings from XDM to standard Analytics fields [here](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/xdm-var-mapping).  | | March 5, 2025 |
| **Product Usage template**  | A new Workspace template allows you to view how the Customer Journey Analytics product is used within your organization. [Learn more](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/templates/use-templates). |  |  March 5, 2025 |
| **Customer Journey Analytics upgrade guide** | Lets you generate a step-by-step guide for upgrading from Adobe Analytics to Customer Journey Analytics. This guide is tailored for your organization and takes into consideration your current Adobe Analytics environment, your intended uses for Customer Journey Analytics, and any time-saving tradeoffs your organization wants to make. To start generating your custom guide, log in to [!DNL Adobe Analytics], then select **[!UICONTROL Upgrade to Customer Journey Analytics]** on the **[!UICONTROL Workspace]** tab. |  | March 13, 2025 |
| **Updates to "No Value" line item on numeric dimensions** | For nuemric dimensions, you can now |  | March 26, 2025 |
| **Adobe Content Analytics** |  Adobe Content Analytics allows you to quickly and easily investigate large volumes of content data to uncover trends, spot anomalies, identify content fatigue, and gain insights from content exposure.<p>Out of the box, you can save time with pre-built reporting templates and new features like Asset Inspector. This capability lets you not only visualize the asset in-line with your data, but also open each asset for summarized details including performance, placements, attributes and more. You can investigate this new set of content data within the context of the complete customer journey to answer important business questions, assess content performance, enhance segmentation, identify optimization opportunities, and define new audiences for activation. Content Analytics is an add-on to Customer Journey Analytics. (Documentation link to follow) |  |  March 27,2025 |
| 
 

## Fixes in Adobe Analytics

**Analysis Workspace**: 
**Classifications**: 
**Component Migration**: 
**Data Feeds**: 
**Data Warehouse**: 
**Mobile App**: 
**Platform**: 
**Report Builder**: 
**Virtual Report Suites**: 
**VISTA rules**: 

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| Data Warehouse-only dimensions | March 12, 2025 | Starting in May 2025, Adobe will begin setting dimensions (custom variables such as eVars and props) which exhibit extremely high cardinality to 'Data Warehouse-only'.  High-cardinality variables have many distinct values; examples include timestamps or UUIDs. These dimensions will no longer be available for reporting in Analysis Workspace.<p>Candidates for this change are dimensions that exceed the low-traffic limits very early in the month. With these types of dimensions, reports in Analysis Workspace which are based on that dimension are not useful because the reportable data represents only a thin slice of the initial values that were collected.<p>Since Data Warehouse does not impose low-traffic limits, you can still build useful reports or segments based on these types of dimensions. |

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | January 17, 2025 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **June 30, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL for Adobe Analytics API (version 1.4)** | July 17, 2024  | On **August 12, 2026**, the following Analytics Legacy API services will reach their end of life and will be shut down, and current integrations built using these services will stop working:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE Authentication</li></ul><p>Integrations that use the Adobe Analytics API (version 1.4) must migrate to the [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/), while WSSE integrations must migrate to an OAuth-based authentication protocol in the [Adobe Developer Console](https://developer.adobe.com/console).</p><p>See the [Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) for answers to common questions and further guidance.</p>  |


## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.26.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2025](/help/release-notes/2025.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Streaming Media Collection release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
