---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (February 2024)

**Last update**: February 6 2024

These release notes cover the release period of February 14, 2024 to March 11, 2024. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| Activity Map for Web SDK without extra cost | Currently, link events are their own events and incur extra cost. This enhancement takes Activity Map link events and packages them into the next hit. |  | February 14, 2024 |
| Increase in default report suite low-traffic thresholds| In **mid April 2024**, Adobe will begin increasing the default report suite low-traffic thresholds as follows: ![low-traffic thresholds](assets/thresholds.png) This will impact only variables which are currently set below the new thresholds. These changes will be made incrementally, and we expect the work to be complete by the **end of May**. As these increases are rolled out, you may notice changes for high-cardinality variables:<ul><li>More dimension values may be available for reporting.</li><li>Segments and calculated metrics may include more data.</li><li>Virtual report suites based on segments may include more data.</li></ul> | Mid April, 2024 | End of May, 2024 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed the following Classifications issues: AN-319515; AN-337559; AN-339327; 

* Fixed the following Classifications Rule Builder issues: AN-339933; 

* Fixed the following A4T issues: 
* Fixed the following Server Call Usage issues:
* Fixed the following Data Warehouse issues:  
* Fixed the following Data Feeds issues: 
* Fixed the following Report Builder issues: 
* Fixed the following Analysis Workspace issues: AN-339600; 

### Other fixes



## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| Adobe API object member additions | January 17, 2024 | Adobe may add optional request and response members (name/value pairs) to existing API objects without notice or changes in versioning. Such additions should be non-breaking changes for your implementation. Adobe recommends that you refer to the API documentation of any third-party tool that you integrate with our APIs so that such additions are ignored in processing if not understood. Adobe will not remove parameters or add required parameters without first providing standard notification through release notes. |
| `getPageLoadTime` plugin deprecated | January 10, 2024 | This plugin is no longer supported. Its code utilizes the performance.timing method, which (according to MDN) has been [deprecated](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). Work on an updated plugin has started. |

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **EOL for [!DNL Reports & Analytics]** | January 10, 2024 | Effective **January 17, 2024**, Adobe discontinued [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer met Adobe's technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process.<p>On January 17, 2024, we terminated many of the associated Reports & Analytics features, including, but not limited to: Scheduled Reports, Data Extracts, and DL Reports. After January 17, 2024, any scheduled reports were no longer sent. In addition, you can no longer schedule future reports as of January 17, 2024.|
| **EOL of [!UICONTROL Publishing Lists] feature** | January 10, 2024 | As part of the EOL of Reports & Analytics, [!UICONTROL Publishing Lists] reached end-of-life on **January 17, 2024**. You can no longer create new or access existing [!UICONTROL Publishing Lists] to send or schedule [!UICONTROL Analysis Workspace] projects. |
| **EOL for Data Workbench** | January 2, 2024 | Adobe end-of-lifed Data Workbench effective **December 31, 2023**. See [Data Workbench end-of-life announcement](https://express.adobe.com/page/GSu6oKOD88GAj/) for details. Contact your organization's Adobe Account Manager with any questions. |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.25.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2023](/help/release-notes/2023.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
