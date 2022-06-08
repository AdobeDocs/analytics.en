---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (May 2022)

**Last update**: June 8, 2022

## Related resources

* [Previous release notes for 2022](/help/release-notes/2022.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)

## New features in Adobe Analytics

| Feature | Description | [Targeted Date](releases.md)  |
| ----------- | ---------- | ------- |
| Populate Lifecycle dimensions and metrics through Experience Edge | Mobile Lifecycle data sent via Experience Edge will now appear in Analytics reporting. See documentation for details on what Lifecycle data is collected via Experience Edge and how it corresponds to existing Lifecycle reporting. [Learn more - coming soon] | May 27, 2022 |

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
| Pausing scheduled reports in Reports & Analytics | June 8, 2022 | On April 21, 2022, we announced the deprecation of several features specific to scheduled reports in preparation for the previously announced [end of life for Reports & Analytics](https://express.adobe.com/page/6WnF8JK6IRDhf/). These features included the ability to schedule new reports as well as new data extracts.<p>In response to customer requests seeking an extension and to ease the transition from Reports and Analytics, we have decided to extend access to these features until **Jan 31, 2023**. Please note that expiration windows for both reports and data extracts will continue to be limited to nine months; report and data extract delivery will pause at the end of this period unless the schedule is reactivated. <p>To reiterate, these features will be deprecated on January 31, 2023, prior to which you will need to migrate your scheduled reporting to one of the other mechanisms available to you in Adobe Analytics. For additional questions or support, please reach out to Adobe Customer Care. |
| Pausing scheduled tasks in Report Builder | June 8, 2022 | On April 21, 2022, we rolled out changes to scheduled tasks in Report Builder as part of our performance and delivery optimization efforts. These changes included removing the ability to have scheduled deliveries “end after x occurrences.” In response to several customer requests seeking more time to explore and implement alternatives, we have decided to restore this option in a limited fashion until **Jan 31, 2023**.<p>You will continue to be able to schedule hourly Report Builder tasks and have them end after a maximum of 99 occurrences. Please note that the rollback only applies to hourly tasks; the “end after x occurrences” will remain unavailable for all other delivery intervals (daily, weekly, monthly, and yearly). Please note that this option will be deprecated on January 31, 2023. For more questions or support, please reach out to Adobe Customer Care. |
| **SFTP upgrade** | May 9, 2022 | Previously, we had communicated that Adobe would upgrade its Secure File Transfer Protocol (SFTP) services in May 2022 to provide improved security for file transfer. We have postponed this upgrade to the **summer of 2022**. When this change takes place, certain SFTP client configurations will no longer be supported. This impacts only data sent to or retrieved from Adobe Analytics using SFTP. The FTP protocol is not impacted. In order to avoid service disruptions, please ensure that your SFTP clients (code, tools, services) are in accordance with the changes detailed [here](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| **Update to browser encryption methods supported for certain customers** | March 28, 2022 | Adobe offers two cipher security levels to meet varying customer needs for security on first-party data collection. On **June 23, 2022** support is removed for certain HTTPS encryption algorithms, known as ciphers, for customers with their security level set to “High”. This action means that some older operating systems are no longer be able to send data to Analytics because they do not support modern encryption methods. Customers using the default “Standard” cipher security settings are not impacted. All customers currently using the “High” setting have already been contacted directly. A detailed list of the ciphers affected by this change can be found here. |
| **2022 ISO region updates** | March 11, 2021 | Adobe plans to perform 2022 ISO region updates on **June 10, 2022**. Expect to see minor geo information updates following this release. |
| **EOL for [!DNL Reports & Analytics]** | January 4, 2022 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe’s technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process. |

{style="table-layout:auto"}

### AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.22.4), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

