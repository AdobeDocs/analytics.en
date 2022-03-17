---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (March 2022)

>[!IMPORTANT]
>
>The following content contains pre-release information and is subject to change.

* For February 2022 release notes, go [here](/help/release-notes/2022.md).
* Learn about the latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html). Get the latest self-help documentation, tutorials, and courses on Experience League.

## New features in Adobe Analytics {#aa-features}

| Feature | Description | [Targeted Date](releases.md)  |
| ----------- | ---------- | ------- |
| Annotations in Workspace | Annotations in Workspace enable you to effectively communicate contextual data nuances and insights to your organization. [Learn more](/help/analyze/analysis-workspace/components/annotations/overview.md) | March 23, 2022 |
| Adobe Analytics landing page updates | Updates to the joint Workspace/Reports & Analytics landing page that improve usability and ease navigation. [Learn more](/help/analyze/landing.md) | TBD |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed an issue that resulted in an error when trying to access Activity Map. (AN-267177)
* Fixed an issue with unsuccessful user asset transfers. (AN-279813)
* Fixed issues with the A4T Workspace panel. (AN-281594; AN-282418)
* Fixed an issue with some users being unable to access Adobe Analytics. (AN-282776)
* Fixed issues with some newly created report suites not collecting data. (AN-283114, AN-283311)
* Fixed issues with being unable to detect Win11 using the Operating System dimension. (AN-275569, AN-275727; AN-280335)
* Fixed issues with incorrectly sent Data Feeds emails. (AN-280255; AN-282051)


### Additional fixes in Adobe Analytics

AN-256929; AN-270937; AN-272158; AN-275130; AN-277830; AN-278635; AN-279066; AN-279683; AN-279899; AN-280504; AN-280617; AN-280663; AN-281423; AN-281523; AN-281608; AN-281671; AN-281963; AN-282027; AN-282218; AN-282593; AN-282605; AN-282632; AN-282654; AN-282694; AN-282744; AN-282756; AN-282804; AN-282838; AN-282862; AN-282903; AN-282937; AN-282892; AN-283315; AN-283338; AN-283388; AN-283417; AN-283474; AN-283511; AN-283691, AN-283895; AN-283943; AN-283957; AN-284030; AN-284100; AN-284142; AN-284162

## Important notices for Adobe Analytics administrators

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| Pausing older scheduled reports | March 11, 2022 | Effective **April 15, 2022**, Adobe intends to pause all scheduled reports that have a creation date greater than two years (created before January 31, 2020). No reports or data will be deleted. Only reports identified as older than two years will be paused, and no additional scheduled reports will be sent. [Learn more](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| 2022 ISO region updates | March 11, 2021 | Adobe will perform 2022 ISO region updates on **June 10, 2022**. Expect to see minor updates following this release. |
| Changing how Analytics handles A4T data collected via Experience Edge | February 25, 2022 | On **March 7th, 2022**, we will change how we handle some Target-related data sent to Adobe Analytics via Experience Edge. When using the Adobe Experience Platform Web SDK with Analytics and Target, some personalization events were counted in [!DNL Adobe Analytics] as [!UICONTROL Page Views]. This led to inflated page view counts and additional server calls. With the change, personalization calls with no Analytics content will be disregarded. Personalization calls with A4T data will record the A4T data, but will not be recorded as billable server calls, nor will it impact page views or link event metrics. |
| Pausing older scheduled Report Builder tasks | February 24, 2022 | **Effective April 15, 2022**, Adobe intends to pause all scheduled Report Builder tasks that were created more than two years ago. Specifically, this pause applies to any tasks created before January 31, 2020. No tasks, workbooks or data will be deleted. However, tasks identified as older than two years will be paused, and no additional scheduled tasks will be sent. [Learn more](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| Expiration of allowlist EOL extension for legacy Analytics OAuth/JWT integrations | January 14, 2022 | On **May 25, 2022**, the [Analytics 1.3 API, 1.4 SOAP API, and Legacy Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) allowlist extension will expire. It was offered to provide customers using legacy [!DNL Adobe Analytics] OAuth/JWT credentials additional time to migrate their client integrations to [Adobe IMS credentials](https://developer.adobe.com/console). This expiration affects (but is not limited to) [!DNL Adobe Analytics Livestream] and [!DNL Adobe Campaign] customers who have not completed their required IMS migrations. Customers who are currently using legacy [!DNL Analytics] OAuth/JWT credentials via the allowlist extension and who do not complete their migration to IMS credentials by May 25, 2022 will lose access to Adobe services. Livestream customers can refer to these [instructions](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) on migrating their client applications to IMS credentials. [!DNL Campaign] customers can reach out to their Adobe account team about upgrading to the latest version of [!DNL Campaign]. |
| Secure File Transfer Protocol (SFTP) services upgrade | March 3, 2022 | On **May 15, 2022**, [!DNL Adobe Analytics] will upgrade its Secure File Transfer Protocol (SFTP) services in order to provide improved security for file transfers. With this change, some SFTP client configurations will no longer be supported. We will also add some connection options which will available by **March 1, 2022**. This impacts only data sent to or retrieved from Adobe Analytics using SFTP. The FTP protocol is not impacted. In order to avoid service disruptions, please ensure that your SFTP clients (code, tools, services) are in accordance with the changes detailed [here](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| EOL for [!DNL Reports & Analytics] | January 4, 2022 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe’s technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process. | 

## AppMeasurement {#appm}

For the latest updates on AppMeasurement releases (Version 2.22.4), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
