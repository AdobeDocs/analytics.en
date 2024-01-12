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
| **Updates to Key Metrics Summary visualization** | N/A | January 17, 2024 | When using the Key Metric Summary visualization, the Comparison date range can now automatically update, depending on whether the Comparison date range option you choose is relative to the primary date range or fixed. [Learn more](/help/analyze/analysis-workspace/visualizations/key-metric.md). |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed the following Classifications issues: AN-314821; AN-326839; AN-332079; AN-332704; AN-332812; AN-332902; AN-332975; AN-333300; AN-333023; AN-333033; AN-333174; AN-333910; AN-334097; AN-334208; AN-334373; AN-334439; AN-334698; AN-334838; AN-334848; AN-334987; AN-335046; AN-335082; AN-335202; AN-335203; AN-335254; AN-335322; AN-335552; AN-335591; AN-335603; AN-335610; AN-335617; AN-335699; AN-335891; AN-335901; AN-336063; AN-336072; AN-336193; AN-336479; AN-336684; AN-336801; AN-337370; AN-337398
* Fixed the following Classifications Rule Builder issues: AN-332390; AN-332573; AN-332718; AN-332927; AN-333248; AN-333953; AN-334647; AN-334736; AN-334910; AN-335642; AN-335683; AN-335811; AN-336033; AN-336569; AN-336852; AN-336875; AN-336902; AN-337190; 
* Fixed the following A4T issues: AN-334564; AN-336178; 
* Fixed the following Server Call Usage issues: AN-332568; AN-333105; AN-333167; AN-333983; AN-334209; AN-334278
* Fixed the following Data Warehouse issues: AN-333010; AN-333076; AN-330227; AN-331580; AN-333350; AN-334291; AN-334283; AN-334287; AN-334301; AN-334385; AN-334453; AN-334977; AN-335079; AN-335171; AN-335245; AN-335426; AN-335680; AN-335818; AN-336087; AN-337308; 
* Fixed the following Data Feeds issues: AN-332241; AN-332366; AN-332617; AN-332654; AN-332702; AN-332723; AN-333014; AN-333166; AN-334037; AN-334125; AN-334211; AN-334216; AN-334235; AN-334976; AN-335158; AN-335368; AN-335408; AN-335468; AN-335471; AN-335528; AN-335596; AN-335662; AN-335733; AN-335883; AN-335894; AN-335968; AN-336098; AN-336192; AN-336243; AN-336659; AN-336977; AN-337117; AN-337219; AN-337262; AN-337393; AN-337462; AN-337854
* Fixed the following Report Builder issues: AN-335246; AN-336311; 
* Fixed the following Analysis Workspace issues: AN-323760; AN-324191; AN-324913; AN-330126; AN-332808; AN-333168; AN-333382; AN-334839; AN-336040; AN-337043; 

### Other fixes

AN-323975; AN-325383; AN-325809; AN-326787; AN-331611; AN-331818; AN-332124; AN-332272; AN-332911; AN-333070; AN-333302; AN-333377; AN-333904; AN-333928; AN-333968; AN-334056; AN-334099; AN-334191; AN-334207; AN-334776; AN-335206; AN-335294; AN-335320; AN-335394; AN-335443; AN-335967; AN-336099; AN-337452; AN-337463

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| `getPageLoadTime` plugin deprecated | January 10, 2024 | This plugin is no longer supported. Its code utilizes the performance.timing method, which (according to MDN) has been [deprecated](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). Work on an updated plugin has started. |

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
