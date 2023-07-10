---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (July 2023)

**Last update**: July 10, 2023

Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## Release highlights {#highlights}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Configure cloud account storage locations for ingesting classification data** | You can now manage cloud account storage locations that are used for classification set automation.<p>[Learn more](/help/components/classifications/importer/configure-import-accounts.md)</p>| N/A |July 10, 2023 |
| **Data Repair filter enhancements** | Three filtering improvements were added to Data Repair:<ul><li>Filter by one variable to modify a second variable. For example, if `eVar2` contains "@" then delete `eVar3`.</li><li>Filter for numeric or non-numeric values</li><li>Apply multiple filters with an AND. For example, where `eVar2="a"` AND `eVar3="b"`</li></ul>[Learn more](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/)| June 21, 2023 |July 12, 2023 |
| **Secure destinations for data feed export** | Data feeds can now be sent to the following cloud storage destinations:<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>Destinations that were previously available (FTP, SFTP, S3, and Azure Blob) are no longer recommended. [Learn more](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html) | June 12, 2023 | July 15, 2023 |
| **Sort components in Analysis Workspace** | A new Sort option is now available when viewing components either in the left rail or in the Data Dictionary in Analysis Workspace. You can sort components by Recommended (those most commonly used), Alphabetical, or Categorical (type).<p>Previously, you could only search or filter components. [Learn more](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | N/A | June 7, 2023 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics



## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **37-month expiration of Purchase IDs and Event IDs (event serialization)**  | July 10,2023 | An upcoming release of the Analytics Hit processing engine, targeted for release on **July 13, 2023**, will start enforcing a 37-month expiration of Purchase IDs and Event IDs (event serialization). Currently, Purchase IDs and Event IDs never expire in Adobe Analytics. Once a Purchase ID or Event ID is seen/used, then any future hit, no matter when, will have that purchase or event marked as a duplicate. With the new processing engine release:<ul><li>Purchase IDs and Event IDs always expire after 37 months.</li><li>If it has been 37 months since the Purchase ID or Event ID was seen, it is no longer considered a duplicate purchase or event.</li><li> If you are "reusing" Purchase IDs or Event IDs from more than 37 months ago, they are no longer considered duplicates.</li></ul> |
| **Migration to AdobeIO OAuth Server-to-Server credentials** | May 11, 2023 | Adobe Analytics API and Livestream customers using AdobeIO JWT credentials must migrate to AdobeIO OAuth Server-to-Server credentials by **January 1, 2025**. For more details and timelines, see the end-of-life notice in the table below.|

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to AdobeIO OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using AdobeIO JWT credentials must migrate to AdobeIO OAuth Server-to-Server credentials by **January 1, 2025**. AdobeIO will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL for [!DNL Reports & Analytics]** | March 7, 2023 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe's technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process.<p>On December 31, 2023, we will terminate many of the associated Reports & Analytics features, including, but not limited to: Scheduled Reports, Data Extracts, and DL Reports. After Dec 31, 2023, any scheduled reports will no longer be sent. In **April 2023**, any reports that were scheduled to expire beyond Dec 31, 2023, will automatically be updated and reverted to expire on Dec 31, 2023. In addition, you can no longer schedule future reports beyond December 31, 2023.|
| **EOL of [!UICONTROL Publishing Lists] feature** | September 29, 2022 | As part of the EOL of Reports & Analytics, [!UICONTROL Publishing Lists] are slated to reach end-of-life in **December 2023**. You will not be able to create new or access existing [!UICONTROL Publishing Lists] to send or schedule [!UICONTROL Analysis Workspace] projects. |
| **EOL for Data Workbench** | September 14, 2022 | Adobe intends to end-of-life Data Workbench effective **December 31, 2023**. See [Data Workbench end-of-life announcement](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) for details. Contact your organization's Adobe Account Manager with any questions. |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.23.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2022](/help/release-notes/2022.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
