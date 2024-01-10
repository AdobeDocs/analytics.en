---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (January 2024)

**Last update**: January 10, 2024

These release notes cover the release period of January 2024 to February 13, 2024. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Data Warehouse updates** | The following Data Warehouse improvements are now available:<ul><li>When creating a Data Warehouse request, users can now make requests available to all users in the organization by enabling the new toggle called [!UICONTROL **Make available to users in your organization**].<p>For more information, see [Data Warehouse request general settings](/help/export/data-warehouse/create-request/dw-general-settings.md).</p></li><li>When creating or managing Data Warehouse report destinations, system administrators can now show accounts and locations that were created by users in the organization by enabling the toggle called [!UICONTROL **Show all destinations**].<p>For more information, see [Configure a report destination for a Data Warehouse request](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).</p></li> | N/A | January 10, 2024 |
| Updates to Key Metrics Summary visualization | N/A | January 17, 2024 | When using the Key Metric Summary visualization, the Comparison date range can now automatically update, depending on whether the Comparison date range option you choose is relative to the primary date range or fixed. [Learn more](/help/analyze/analysis-workspace/visualizations/key-metric.md). |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

TBD

### Other fixes

TBD

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| `getPageLoadTime` plugin deprecated | January 10, 2024 | This plugin is no longer supported. Its code utilizes the performance.timing method, which (according to MDN) has been [deprecated](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). |

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **EOL for [!DNL Reports & Analytics]** | January 10, 2024 | Effective **January 17, 2024**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe's technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process.<p>On December 31, 2023, we will terminate many of the associated Reports & Analytics features, including, but not limited to: Scheduled Reports, Data Extracts, and DL Reports. After Dec 31, 2023, any scheduled reports will no longer be sent. In **April 2023**, any reports that were scheduled to expire beyond Dec 31, 2023, were automatically updated and reverted to expire on Dec 31, 2023. In addition, you can no longer schedule future reports beyond December 31, 2023.|
| **EOL of [!UICONTROL Publishing Lists] feature** | January 10, 2024 | As part of the EOL of Reports & Analytics, [!UICONTROL Publishing Lists] are slated to reach end-of-life on **January 17, 2024**. You will not be able to create new or access existing [!UICONTROL Publishing Lists] to send or schedule [!UICONTROL Analysis Workspace] projects. |
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
