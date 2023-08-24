---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (August 2023)

**Last update**: August 24, 2023

These release notes cover the release period of August 9 to September 13, 2023. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Classification sets in API 2.0** |  Provides Adobe Analytics API 2.0 methods for saving, deleting, retrieving, importing, and exporting classification set data. | N/A | August 30, 2023 |
| **Reporting Activity Manager** | The Reporting Activity Manager provides administrators with detailed visibility into reporting consumption for each report suite, allowing admins to easily diagnose and then fix capacity issues during peak reporting times. [Learn more](/help/admin/admin/reporting-activity.md) | N/A | September 12, 2023 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed an issue with custom events not getting loaded. (AN-324163)
* Fixed an issue with being unable to edit labels for the legends in a visualization. (AN-323246)

AN-315605; AN-316306; AN-317494; AN-317844; AN-320424; AN-320597; AN-320680; AN-320869; AN-321624; AN-321693; AN-322009; AN-322244; AN-322380; AN-322432; AN-322466; AN-322556; AN-322669; AN-322735; AN-323151; AN-323220; AN-323380; AN-323492; AN-323595; AN-323755; AN-323854; AN-323916; AN-324044; AN-324200; AN-324213; AN-324238; AN-324347; AN-323598; AN-323625; AN-323631; AN-323638; AN-323641; AN-323755; AN-323767; AN-323777; AN-323825; AN-323846; AN-323972; AN-324113; AN-324170; AN-324197; AN-324273; AN-324275; AN-324345; AN-324384; AN-324433; AN-324511; AN-324513; AN-324521; AN-324524; AN-324531; AN-324532; AN-324534; AN-324537; AN-324569; AN-324618; AN-324635; AN-324688; AN-324704; AN-324712; AN-324721; AN-324745; AN-324792; AN-324793; AN-324794; AN-324795; AN-324824; AN-324905; AN-324918; AN-324932; AN-324934; AN-324947; AN-325003; AN-325073; AN-325143; AN-325148; AN-325153; AN-325177; AN-325187; AN-325252; AN-325305; AN-325363; AN-325401; AN-325439; AN-325431; AN-325491; AN-325495; AN-325508; AN-325594; AN-325601; AN-325660; AN-325779; AN-325857; AN-325883; AN-325885; AN-325886


## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **37-month expiration of Purchase IDs and Event IDs (event serialization)**  | July 10,2023 | An upcoming release of the Analytics Hit processing engine, targeted for release on **July 13, 2023**, will start enforcing a 37-month expiration of Purchase IDs and Event IDs (event serialization). Currently, Purchase IDs and Event IDs never expire in Adobe Analytics. Once a Purchase ID or Event ID is seen/used, then any future hit, no matter when, will have that purchase or event marked as a duplicate. With the new processing engine release:<ul><li>Purchase IDs and Event IDs always expire after 37 months.</li><li>If it has been 37 months since the Purchase ID or Event ID was seen, it is no longer considered a duplicate purchase or event.</li><li> If you are "reusing" Purchase IDs or Event IDs from more than 37 months ago, they are no longer considered duplicates.</li></ul> |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 | Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. For more details and timelines, see the end-of-life notice in the table below.|

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL for [!DNL Reports & Analytics]** | March 7, 2023 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe's technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process.<p>On December 31, 2023, we will terminate many of the associated Reports & Analytics features, including, but not limited to: Scheduled Reports, Data Extracts, and DL Reports. After Dec 31, 2023, any scheduled reports will no longer be sent. In **April 2023**, any reports that were scheduled to expire beyond Dec 31, 2023, will automatically be updated and reverted to expire on Dec 31, 2023. In addition, you can no longer schedule future reports beyond December 31, 2023.|
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
