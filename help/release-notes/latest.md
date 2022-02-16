---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (February 2022)

>[!IMPORTANT]
>
>These release notes contain pre-release information that is subject to change.

**Last update**: February 10, 2022

Learn about the latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html). Get the latest self-help documentation, tutorials, and courses on Experience League.

## New features in Adobe Analytics {#aa-features}

| Feature | Description | [Targeted Date](releases.md)  |
| ----------- | ---------- | ------- |
| Mobile scorecard project preview mode | Launch a preview of how your mobile scorecard will look in the Analytics dashboards app, directly from the scorecard builder. The preview mode allows users to interact with filters and charts in the same way they would in the app, allowing them to preview the experience before they save and share the scorecard. Users can also use the device picker in preview mode to see how their scorecard will look on different devices. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=en#preview) | February 16, 2022 |
| API projects endpoint | Add, edit or delete Analysis Workspace projects using the API. [Learn more](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) | Feb 1, 2022 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed a number of issues with [!UICONTROL Server call usage]. (AN-279134, AN-279878, AN-280802, AN-279097, AN-191284, AN-269720)
* Fixed an issue that cause Data Warehouse to export empty .csv files. (AN-280291)
* Fixed an issue that caused Audience Names to not be populated for recent segments. (AN-279715)
* Fixed an issue with slow reporting times. (AN-280055)
* Fixed issues with Classifications not classifying all dimension items. (AN-280031)

### Additional fixes in Adobe Analytics

AN-268093, AN-273820, AN-274435, AN-274904, AN-275356, AN-275947, AN-276160, AN-276258, AN-276705, AN-277051, AN-277957, AN-278693, AN-278882, AN-279000, AN-279046, AN-279362, AN-279460, AN-279488, AN-279554, AN-279572, AN-279663, AN-279755, AN-279825, AN-280002, AN-280013, AN-280019, AN-280033, AN-280086, AN-280232, AN-280264, AN-280288, AN-280342, AN-280347, AN-280360, AN-280370, AN-280724, AN-280830, AN-280941, AN-281353, AN-281424, AN-281533

## Important notices for [!DNL Analytics] administrators

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
|Expiration of allowlist EOL extension for legacy Analytics OAuth/JWT integrations | January 14, 2022 | On **May 25, 2022**, the [Analytics 1.3 API, 1.4 SOAP API, and Legacy Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) allowlist extension will expire. It was offered to provide customers using legacy [!DNL Adobe Analytics] OAuth/JWT credentials additional time to migrate their client integrations to [Adobe IMS credentials](https://developer.adobe.com/console). This expiration affects (but is not limited to) [!DNL Adobe Analytics Livestream] and [!DNL Adobe Campaign] customers who have not completed their required IMS migrations. Customers who are currently using legacy [!DNL Analytics] OAuth/JWT credentials via the allowlist extension and who do not complete their migration to IMS credentials by May 25, 2022 will lose access to Adobe services. Livestream customers can refer to these [instructions](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) on migrating their client applications to IMS credentials. [!DNL Campaign] customers can reach out to their Adobe account team about upgrading to the latest version of [!DNL Campaign]. |
| EOL for [!DNL Reports & Analytics] | January 4, 2022 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe’s technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process. | 
| Secure File Transfer Protocol (SFTP) services upgrade | January 13, 2022 | On **May 2, 2022**, [!DNL Adobe Analytics] will upgrade its Secure File Transfer Protocol (SFTP) services in order to provide improved security for file transfers. With this change, some SFTP client configurations will no longer be supported. We will also add some connection options which will available by **March 1, 2022**. This impacts only data sent to or retrieved from Adobe Analytics using SFTP. The FTP protocol is not impacted. In order to avoid service disruptions, please ensure that your SFTP clients (code, tools, services) are in accordance with the changes detailed [here](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |

## AppMeasurement {#appm}

For the latest updates on AppMeasurement releases (Version 2.22.4), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
