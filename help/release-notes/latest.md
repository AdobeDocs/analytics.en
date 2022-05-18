---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (May 2022)

**Last update**: May 17, 2022

## Related resources

* [Previous release notes for 2022](/help/release-notes/2022.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)

## New features in Adobe Analytics

| Feature | Description | [Targeted Date](releases.md)  |
| ----------- | ---------- | ------- |
| Populate Lifecycle dimensions and metrics through Experience Edge | Many Lifecycle events are now automatically mapped to XDM fields. Events that are not automatically mapped can be sent to Adobe through free-form key/value pairs. [Learn more - coming soon] | May 27, 2022 |

{style="table-layout:auto"}

### Fixes in Adobe Analytics

(Fixes for multiple customers)

N/A

### Additional fixes in Adobe Analytics

(Fixes for individual customers)

AN-274429; AN-279640; AN-280918; AN-280945; AN-282884; AN-283565; AN-284785; AN-284814; AN-284854; AN-284989; AN-285244; AN-285253; AN-285432; AN-285528; AN-285535; AN-285710; AN-286255; AN-286340; AN-286434; AN-286454; AN-286630; AN-286716; AN-286854; AN-286911

### Important notices for Adobe Analytics administrators

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **SFTP upgrade** | May 9, 2022 | Previously, we had communicated that Adobe would upgrade its Secure File Transfer Protocol (SFTP) services in May 2022 to provide improved security for file transfer. We have postponed this upgrade to the summer of 2022. When this change takes place, certain SFTP client configurations will no longer be supported. This impacts only data sent to or retrieved from Adobe Analytics using SFTP. The FTP protocol is not impacted. In order to avoid service disruptions, please ensure that your SFTP clients (code, tools, services) are in accordance with the changes detailed [here](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| **Cross-Device Analytics (CDA) entitlement** | April 13, 2022 | Effective **May 1, 2022**, any new implementations of [CDA](/help/components/cda/overview.md) are limited to a maximum of three report suite IDs (RSIDs) per customer. |
| **Change to how Adobe Analytics handles A4T data collected via Experience Edge** | March 31, 2022 | On March 7, 2022, Analytics changed how it handles some calls coming from Experience Edge that include Target content intended for Analytics for Target (A4T) reporting. Starting March 7, all hits with A4T reporting content are modified so they are not treated as Page View or Link events. Starting **March 31, 2022**, the logic is more selective so that standard Page View and Click events are not modified. Going forward, the only events that are modified are personalization-only calls that only have A4T content. |
| **Update to browser encryption methods supported for certain customers** | March 28, 2022 | Adobe offers two cipher security levels to meet varying customer needs for security on first-party data collection. On **June 23, 2022** support is removed for certain HTTPS encryption algorithms, known as ciphers, for customers with their security level set to “High”. This action means that some older operating systems are no longer be able to send data to Analytics because they do not support modern encryption methods. Customers using the default “Standard” cipher security settings are not impacted. All customers currently using the “High” setting have already been contacted directly. A detailed list of the ciphers affected by this change can be found here. |
| **Pausing older scheduled reports** | April 12, 2022 | Effective **April 20, 2022**, Adobe intends to pause all scheduled reports that have a creation date greater than two years (created before January 31, 2020). No reports or data are deleted. Only reports identified as older than two years are paused, and no additional scheduled reports are sent. Learn more |
| **2022 ISO region updates** | March 11, 2021 | Adobe plans to perform 2022 ISO region updates on **June 10, 2022**. Expect to see minor geo information updates following this release. |
| **Pausing older scheduled Report Builder tasks** | April 12, 2022 | Effective **April 20, 2022**, Adobe intends to pause all scheduled Report Builder tasks that were created more than two years ago. Specifically, this pause applies to any tasks created before January 31, 2020. No tasks, workbooks, or data are deleted. However, tasks identified as older than two years are paused, and no additional scheduled tasks are sent. Learn more |
|**Expiration of allowlist EOL extension for legacy Analytics OAuth/JWT integrations** | January 14, 2022 | On **May 25, 2022**, the [Analytics 1.3 API, 1.4 SOAP API, and Legacy Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) allowlist extension expires. It was offered to provide customers using legacy [!DNL Adobe Analytics] OAuth/JWT credentials additional time to migrate their client integrations to [Adobe IMS credentials](https://developer.adobe.com/console). This expiration affects (but is not limited to) [!DNL Adobe Analytics Livestream] and [!DNL Adobe Campaign] customers who have not completed their required IMS migrations. Customers who are currently using legacy [!DNL Analytics] OAuth/JWT credentials via the allowlist extension and who do not complete their migration to IMS credentials by May 25, 2022 loses access to Adobe services. Livestream customers can refer to these [instructions](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) on migrating their client applications to IMS credentials. [!DNL Campaign] customers can reach out to their Adobe account team about upgrading to the latest version of [!DNL Campaign]. |
| **EOL for [!DNL Reports & Analytics]** | January 4, 2022 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe’s technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process. |

{style="table-layout:auto"}

### AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.22.4), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

