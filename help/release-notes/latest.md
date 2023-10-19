---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (October/November 2023)

**Last update**: October 19, 2023

These release notes cover the release period of October 23, 2023 to end of November, 2023. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Reporting Activity Manager enhancements** | The Reporting Activity Manager lets you see the reporting capacity for each report suite in your organization.  It provides administrators with detailed visibility into reporting consumption in order to easily diagnose and fix capacity issues during peak reporting times. Following are some of the enhancements now available in the Reporting Activity Manager: <ul><li>Restrict subsequent requests: In addition to canceling current requests, administrators can now restrict requests for a defined time period. Administrators can restrict requests by Request, Project, and User.</li><li>In addition to Utilization and Capacity metrics, the Reporting Activity Manager now includes more data about reporting activity: Complexity column, User column, and Connection column.</li><li>All cancelations and restrictions made in the Reporting Activity manager are now visible in the Audit Log. Administrators can use the Audit Log to view what is currently canceled. Cancelations cannot be reversed in the Reporting Activity Manager or in the Audit Log.</li></ul><p>For more information, see [Reporting Activity Manager overview](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)</p> | October 17, 2023 | October 23, 2023|
| **Data Warehouse improvements** | When creating a Data Warehouse request, you can now configure a cloud account to use as the report destination. The following cloud account types are available for sending data:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Email (this option was previously available)</li></ul>FTP, SFTP, Azure Blob, and S3 are still available as report destinations, but are no longer recommended.<p>The user experience when creating and managing Data Warehouse requests has also been improved. For more information, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md) and [Manage Data Warehouse requests](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html). | September 12, 2023 | October 25, 2023 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Analytics Processing and Reporting Engine changes deployed during the last week of October will fix an issue where the labels for Page or Link dimensions may incorrectly show as `Unknown`. Prior to the fix, the `Unknown` labels may have shown up incorrectly when a Page Name or Link Name was not passed in on a hit, defaulting to Page URL and Link URL respectively. These dimensions were configured to be case insensitive. With this fix, reports going forward will be correct. But for reports on historic data, some report results may still be incorrectly labeled as `Unknown`. (AN-328030)





## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **Full IP obfuscation for Adobe Experience Edge hits** | September 27, 2023 | IP obfuscation for hits coming from Experience Edge will be updated later in October of 2023. In April, Experience Edge added the ability to obfuscate IP addresses. At that time, Adobe Analytics only supported partial obfuscation of IPs, due to the way Analytics processes hits from Experience Edge. When customers chose full obfuscation for Experience Edge, Analytics only received partially obfuscated IPs. When this change is implemented, Analytics will receive the fully obfuscated IP.|
| **Adobe Analytics Livestream - Analytics 2.0 APIs** | September 27, 2023 | Customers can now access the [Endpoint guide for Adobe Analytics Livestream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/) under the Adobe Analytics 2.0 APIs instead in its previous location, with the 1.4 APIs. Note that customers using Adobe I/O JWT credentials must migrate to  Adobe I/O OAuth Server-to-Server credentials by January 1, 2025. (See details under EOL notices below.) |

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL for [!DNL Reports & Analytics]** | March 7, 2023 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe's technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process.<p>On December 31, 2023, we will terminate many of the associated Reports & Analytics features, including, but not limited to: Scheduled Reports, Data Extracts, and DL Reports. After Dec 31, 2023, any scheduled reports will no longer be sent. In **April 2023**, any reports that were scheduled to expire beyond Dec 31, 2023, were automatically updated and reverted to expire on Dec 31, 2023. In addition, you can no longer schedule future reports beyond December 31, 2023.|
| **EOL of [!UICONTROL Publishing Lists] feature** | September 29, 2022 | As part of the EOL of Reports & Analytics, [!UICONTROL Publishing Lists] are slated to reach end-of-life in **December 2023**. You will not be able to create new or access existing [!UICONTROL Publishing Lists] to send or schedule [!UICONTROL Analysis Workspace] projects. |
| **EOL for Data Workbench** | September 14, 2022 | Adobe intends to end-of-life Data Workbench effective **December 31, 2023**. See [Data Workbench end-of-life announcement](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) for details. Contact your organization's Adobe Account Manager with any questions. |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.25.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2022](/help/release-notes/2022.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
