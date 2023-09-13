---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (September 2023)

**Last update**: September 13, 2023

The September release notes cover the release period of September 13, 2023 to October 3, 2023. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Classification in API 2.0** |  Provides Adobe Analytics API 2.0 methods for saving, deleting, retrieving, importing, and exporting classification set data. [Learn more](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/) | N/A | September 13, 2023 |
| **Support for new `correlationID` field for A4T classifications** | The `_experience.decisioning.propositions.scopeDetails.correlationID` field is now available in the Adobe Analytics source connector schema. We are adding this ID for easy joining of classification data for Adobe Target activities and experience events. | N/A | September 13, 2023 |
| **Data Warehouse improvements** | When creating a Data Warehouse request, you can now configure a cloud account to use as the report destination. The following cloud account types are available for sending data:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Email (this option was previously available)</li></ul>FTP, SFTP, Azure Blob, and S3 are still available as report destinations, but are no longer recommended.<p>The user experience when creating and managing Data Warehouse requests has also been improved. For more information, see [Create a Data Warehouse request](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/create-request/t-dw-create-request.html) and [Manage Data Warehouse requests](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html). | September 13, 2023 | October 4, 2023 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed an issue that prevented Classification data from showing up in Workspace. (AN-326827)

## Other fixes

AN-314882; AN-315591; AN-318165; AN-318559; AN-319031; AN-319244; AN-321657; AN-321759; AN-323099; AN-323596; AN-323640; AN-324442; AN-324921; AN-324953; AN-324977; AN-324979; AN-325124; AN-325395; AN-325433; AN-325535; AN-325693; AN-325720; AN-325835; AN-325880; AN-325957; AN-325984; AN-326054; AN-326065; AN-326136; AN-326155; AN-326162; AN-326235; AN-326317; AN-326344; AN-326357; AN-326359; AN-326433; AN-326438; AN-326440; AN-326461; AN-326464; AN-326523; AN-326553; AN-326606; AN-326635; AN-326642; AN-326652; AN-326678; AN-326769; AN-326777; AN-326830; AN-326938; AN-326949; AN-327081; AN-327082; AN-327085; AN-327103; AN-327198; AN-327225; AN-327275; AN-327358; AN-327423; AN-327561; AN-327755; AN-327896; AN-327922; AN-328128; AN-328300; AN-328428; AN-328518; AN-328554

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| N/A | N/A | N/A |

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

For the latest updates on AppMeasurement releases (Version 2.24.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2022](/help/release-notes/2022.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
