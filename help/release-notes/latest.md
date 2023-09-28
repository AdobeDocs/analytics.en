---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (October 2023)

**Last update**: September 28, 2023

The October release notes cover the release period of October 4, 2023 to October 24, 2023. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **New columns available when managing components** | The following new columns are now available when managing components:<ul><li>Used in<p>This column is available in the [Calculated metrics manager](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) and the [Segments manager](/help/components/segmentation/segmentation-workflow/seg-manage.md).</p></li><li>Last used<p>This column is available in the [Calculated metrics manager](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md), the [Segments manager](/help/components/segmentation/segmentation-workflow/seg-manage.md), and the [Alerts manager](/help/components/c-alerts/alert-manager.md).</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified. You can use the Data Dictionary along with this information to help you keep track of and better understand how components are being used in your organization.</p> | September 20, 2023 | October 4, 2023 |
| **Reporting Activity Manager enhancements** | The Reporting Activity Manager lets you see the reporting capacity for each report suite in your organization.  It provides administrators with detailed visibility into reporting consumption in order to easily diagnose and fix capacity issues during peak reporting times. Following are some of the enhancements now available in the Reporting Activity Manager: <ul><li>Restrict subsequent requests: In addition to canceling current requests, administrators can now restrict requests for a defined time period. Administrators can restrict requests by Request, Project, and User.</li><li>In addition to Utilization and Capacity metrics, the Reporting Activity Manager now includes more data about reporting activity: Complexity column, User column, and Connection column.</li><li>All cancelations and restrictions made in the Reporting Activity manager are now visible in the Audit Log. Administrators can use the Audit Log to view what is currently canceled. Cancelations cannot be reversed in the Reporting Activity Manager or in the Audit Log.</li></ul>Learn more (coming soon) | N/A | October 4, 2023|
| **Data Warehouse improvements** | When creating a Data Warehouse request, you can now configure a cloud account to use as the report destination. The following cloud account types are available for sending data:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Email (this option was previously available)</li></ul>FTP, SFTP, Azure Blob, and S3 are still available as report destinations, but are no longer recommended.<p>The user experience when creating and managing Data Warehouse requests has also been improved. For more information, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md) and [Manage Data Warehouse requests](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html). | September 12, 2023 | October 3, 2023 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed issues where A4T reports were not appearing in the Target/Analytics UI. (AN-329375, AN-329745)

AN-313983; AN-324189; AN-325095; AN-325677; AN-325886; AN-326068; AN-326360; AN-326458; AN-327290; AN-327315; AN-327353; AN-327505; AN-327589; AN-327609; AN-327922; AN-328110; AN-328222; AN-328261; AN-328496; AN-328577; AN-328629; AN-328736; AN-328888; AN-328899; AN-328902; AN-328921; AN-328958; AN-329208; AN-329277; AN-329332; AN-329334; AN-329335; AN-329336; AN-329357; AN-329385; AN-329387; AN-329397; AN-329463; AN-329501; AN-329504; AN-329505; AN-329515; AN-329524; AN-329526; AN-329534; AN-329539; AN-329541; AN-329543; AN-329545; AN-329564; AN-329570; AN-329623; AN-329624; AN-329636; AN-329646; AN-329647; AN-329668; AN-329701; AN-329737; AN-329741; AN-329751; AN-329812; AN-329813; AN-329821; AN-329824; AN-329833; AN-329848; AN-329852; AN-329861; AN-329863; AN-329874; AN-329882; AN-329911; AN-329917; AN-329942; AN-329954; AN-329968; AN-329971; AN-329982; AN-330026; AN-330044; AN-330131; AN-330132

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
