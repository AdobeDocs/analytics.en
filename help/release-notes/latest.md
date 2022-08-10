---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (August 2022)

**Last update**: August 10, 2022

## Related resources

* [Previous release notes for 2022](/help/release-notes/2022.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)

## New or updated features in Adobe Analytics

| Feature | Description | [Targeted Date](releases.md)  |
| ----------- | ---------- | ------- |
| Updates to the Data Warehouse UI and the Data Feeds UI to include new delivery types | New Data Feed and Data Warehouse delivery types include: Amazon S3, Azure Blob SAS, Google Cloud Platform. More information to follow. | August 17, 2022 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed several data feed-related issues. (AN-297264, AN-297295, AN-297449)

**Fixes for individual customers**: 

AN-280956; AN-285670; AN-288176; AN-289221; AN-289665; AN-289768; AN-294632; AN-294970; AN-295078; AN-295233; AN-295482; AN-295549; AN-295633; AN-295712; AN-295749; AN-295963; AN-295977; AN-296094; AN-296153; AN-296167; AN-296177; AN-296297; AN-296383; AN-296394; AN-296414; AN-296431; AN-296459; AN-296486; AN-296510; AN-296514; AN-296540; AN-296734; AN-296840; AN-296841; AN-296977; AN-296987; AN-297002; AN-297141; AN-297267; AN-297396; 

## Important notices for Adobe Analytics administrators

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **Update to new NetAcuity carrier database** | July 11, 2022 | **Starting in October, 2022**, carrier-related information stored in the `carrier` field in Adobe Analytics Data Warehouse and Analytics Data Feeds will change. Historically, the data format in that column has been `<domain>:<ISP>`. Adobe has maintained an internal lookup table to map these `<domain>:<ISP>` values into carrier names for reporting purposes in Adobe Analytics reporting tools (Analysis Workspace, Reports & Analytics, reporting API, data warehouse, LiveStream, etc.). The lookup file (`carrier.tsv`) is also provided with Data Feeds so that you can use the same mappings.<p>This update enhances our carrier mappings by using a more accurate carrier database from NetAcuity. The format of the data in the carrier column in Data Feeds will change going forward. Instead of `<domain>:<ISP>`, it will contain a carrier name. Adobe will continue to use the lookup table in order to maintain as much continuity with past reporting as possible. Reporting tools where the lookups are applied by Adobe (Analysis Workspace, Reports & Analytics, reporting API, data warehouse, LiveStream, etc.) will benefit from more accurate mappings. Some mappings – especially for international domains and ISPs – will change more than others when we adopt the new database. The data feeds carrier lookup file (`carrier.tsv`) will maintain the old mappings and add the new mappings.<p>The Analytics Source Connector does not currently map the carrier field, so carrier reporting is not currently available in AEP, CJA etc. Therefore, use of the new carrier database will not impact anything in AEP that is based on data provided by the Analytics Source Connector. |
| **Improved IP-to-geolocation mapping** | July 11, 2022 | Our vendor for IP lookups, Digital Element, is upgrading to a new improved dataset (NetAcuity Pulse) for IP-to-geolocation mapping. Adobe Analytics will adopt this new dataset in the **October, 2022** timeframe. The new database will be more accurate than previous versions. Some IP-to-geo mappings will change/improve when the new database is adopted.<p>All Adobe Analytics tools (Analysis Workspace, Reports & Analytics, reporting API, data warehouse, LiveStream, data feeds etc.) will automatically take advantage of the new improved mappings. There will be no change in the format of the data in data feeds. CJA data provided through the Analytics Source Connector will also automatically take advantage of the new mappings. | 
| **Pausing scheduled reports in Reports & Analytics** | June 8, 2022 | On April 21, 2022, we announced the deprecation of several features specific to scheduled reports in preparation for the previously announced end of life for Reports & Analytics. These features included the ability to schedule new reports as well as new data extracts.<p>In response to customer requests seeking an extension and to ease the transition from Reports and Analytics, we have decided to extend access to these features until **Jan 31, 2023**. Please note that expiration windows for both reports and data extracts will continue to be limited to nine months; report and data extract delivery will pause at the end of this period unless the schedule is reactivated.<p>To reiterate, these features will be deprecated on January 31, 2023. Before this date, you must migrate your scheduled reporting to one of the other mechanisms available to you in Adobe Analytics. For additional questions or support, please reach out to Adobe Customer Care. [Learn more](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausing scheduled tasks in Report Builder** | June 8, 2022 | On April 21, 2022, we rolled out changes to scheduled tasks in Report Builder as part of our performance and delivery optimization efforts. These changes included removing the ability to have scheduled deliveries “end after x occurrences.” In response to several customer requests seeking more time to explore and implement alternatives, we have decided to restore this option in a limited fashion until **Jan 31, 2023**.<p>You can continue to schedule hourly Report Builder tasks and have them end after a maximum of 99 occurrences. Please note that the rollback only applies to hourly tasks; the “end after x occurrences” will remain unavailable for all other delivery intervals (daily, weekly, monthly, and yearly). Please note that this option will be deprecated on January 31, 2023. For more questions or support, please reach out to Adobe Customer Care. [Learn more](/help/analyze/report-builder/r-arb-scheduled-reports.md)|
| **SFTP upgrade** | May 9, 2022 | Previously, we had communicated that Adobe would upgrade its Secure File Transfer Protocol (SFTP) services in May 2022 to provide improved security for file transfer. We have postponed this upgrade to the **summer of 2022**. When this change takes place, certain SFTP client configurations will no longer be supported. This impacts only data sent to or retrieved from Adobe Analytics using SFTP. The FTP protocol is not impacted. In order to avoid service disruptions, please ensure that your SFTP clients (code, tools, services) are in accordance with the changes detailed [here](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| **EOL for [!DNL Reports & Analytics]** | January 4, 2022 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe’s technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process. |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.22.4), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

