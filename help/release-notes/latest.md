---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (October/November 2022)

**Last update**: October 28, 2022

Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features in Adobe Analytics

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **[!UICONTROL Key metric summary]** visualization | The [!UICONTROL Key metric summary] visualization lets you see how an important metrics is trending within a single timeframe. It also lets you compare metric performance across two timeframes. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=en) | October 5, 2022 | October 19, 2023 |
| **Case-insensitive multi-value variables** | For case-insensitive multi-value variables, the values stored in `mvvar1 - mvvar3` and `post_mvvar1 - post_mvvar3` in Data Feeds will no longer be automatically lowercased. Instead, data feeds (and data passed through the Analytics Source Connector to Adobe Experience Platform and CJA) will reflect the original case that was passed in from the page. | N/A | October 24, 2022 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed an issue where recent MacOS versions were incorrectly named "Macintosh". With this fix, the OS dimension will begin using "MacOS" version numbering, starting with MacOS 11. (AN-301834)
* Fixed an issue with the "fixed dates" date range in Report Builder. (AN-303684)
* Fixed issues with the Data Feed UI not loading. (AN-303803, AN-303784)

### Other fixes

AN-295574; AN-296354; AN-297143; AN-299501; AN-301755; AN-302054; AN-302304; AN-302631; AN-302811; AN-303090; AN-303372; AN-303428; AN-303429; AN-303432; AN-303434; AN-303437; AN-303438; AN-303519; AN-303610; AN-303656; AN-303659; AN-303663; AN-303664; AN-303818; AN-303823; AN-303837; AN-304036;  AN-304195; AN-304321; AN-304325; AN-304339; AN-304356; AN-304435; AN-304457; AN-304509; AN-304519; AN-304534 

## Important notices for Adobe Analytics administrators

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **Update to device lookups due to Google Client Hints** | October 14, 2022 | The use of client hints in device lookup, originally planned for October 26, 2022, has been postponed to **January 2023**. <p> <p>As of October 2022 it is possible to collect client hints with either the Web SDK or AppMeasurement JavaScript libraries. But client hints will not be incorporated into device lookup until January 2023. At that date, Adobe will begin using client hints in addition to the User-Agent when deriving certain device information for hits coming from Chromium browsers, such as Google Chrome and Microsoft Edge. This is in response to Google's plan to gradually reduce the information presented from the User-Agent string in lieu of data passed via client hints. <p> <p>As part of this change, Adobe will use Device Atlas for all device lookups related to User-Agent. [Learn more](/help/technotes/client-hints.md)|
| **Default landing page** | September 29, 2022 |The [new landing page](/help/analyze/landing.md) that was introduced earlier this year will become the default experience for all users in **January 2023**. The current page will be deprecated and everyone will be required to use the new experience. |
| **[!UICONTROL Anomaly detection] auto-run conditions** | September 29, 2022 | Today, [!UICONTROL Anomaly detection] auto-runs on all columns of time-series freeform tables. To ensure data is available for analysis and projects load faster, Adobe will change how Anomaly detection auto-runs. Starting **October 26, 2022**, [!UICONTROL Anomaly detection] will auto-run only on the first metric column in a table. You can configure column settings to run anomaly detection on other columns, if needed. |
| **Update to new NetAcuity carrier database** | September 26, 2022 | This update, originally planned for on October 5, 2022, has been postponed to **January, 2023**. Carrier-related information stored in the `carrier` field in Adobe Analytics Data Warehouse and Analytics Data Feeds will change. Historically, the data format in that column has been `<domain>:<ISP>`. Adobe has maintained an internal lookup table to map these `<domain>:<ISP>` values into carrier names for reporting purposes in Adobe Analytics reporting tools (Analysis Workspace, Reports & Analytics, reporting API, Data Warehouse, LiveStream, etc.). The lookup file (`carrier.tsv`) is also provided with Data Feeds so that you can use the same mappings.<p>This update enhances our carrier mappings by using a more accurate carrier database from NetAcuity. The format of the data in the carrier column in Data Feeds will change going forward. Instead of `<domain>:<ISP>`, it will contain a carrier name. Adobe will continue to use the lookup table in order to maintain as much continuity with past reporting as possible. Reporting tools where the lookups are applied by Adobe (Analysis Workspace, Reports & Analytics, reporting API, data warehouse, LiveStream, etc.) will benefit from more accurate mappings. Some mappings – especially for international domains and ISPs – will change more than others when Adobe adopts the new database. The data feeds carrier lookup file (`carrier.tsv`) will maintain the old mappings and add the new mappings.<p>The Analytics Source Connector does not currently map the carrier field, so carrier reporting is not currently available in Experience Platform, CJA etc. Therefore, use of the new carrier database will not impact anything in Experience Platform that is based on data provided by the Analytics Source Connector. |
| **Improved IP-to-geolocation mapping** | September 26, 2022 | Our vendor for IP lookups, Digital Element, is upgrading to a new improved dataset (NetAcuity Pulse) for IP-to-geolocation mapping. Originally planned for October 2022, Adobe Analytics will adopt this new dataset in **January, 2023**. The new database will be more accurate than previous versions. Some IP-to-geo mappings will change/improve when the new database is adopted.<p>All Adobe Analytics tools (Analysis Workspace, Reports & Analytics, reporting API, data warehouse, LiveStream, data feeds etc.) will automatically take advantage of the new improved mappings. There will be no change in the format of the data in data feeds. CJA data provided through the Analytics Source Connector will also automatically take advantage of the new mappings. |
| **Pausing scheduled reports in Reports & Analytics** | June 8, 2022 | On April 21, 2022, Adobe announced the deprecation of several features specific to scheduled reports in preparation for the previously announced end of life for Reports & Analytics. These features included the ability to schedule new reports as well as new data extracts.<p>In response to customer requests seeking an extension and to ease the transition from Reports & Analytics, Adobe has decided to extend access to these features until **Jan 31, 2023**. Please note that expiration windows for both reports and data extracts will continue to be limited to nine months; report and data extract delivery will pause at the end of this period unless the schedule is reactivated.<p>To reiterate, these features will be deprecated on January 31, 2023. Before this date, you must migrate your scheduled reporting to one of the other mechanisms available to you in Adobe Analytics. For additional questions or support, please reach out to Adobe Customer Care. [Learn more](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausing scheduled tasks in Report Builder** | June 8, 2022 | On April 21, 2022, Adobe rolled out changes to scheduled tasks in Report Builder as part of our performance and delivery optimization efforts. These changes included removing the ability to have scheduled deliveries "end after x occurrences." In response to several customer requests seeking more time to explore and implement alternatives, Adobe has decided to restore this option in a limited fashion until **Jan 31, 2023**.<p>You can continue to schedule hourly Report Builder tasks and have them end after a maximum of 99 occurrences. Please note that the rollback only applies to hourly tasks; the "end after x occurrences" will remain unavailable for all other delivery intervals (daily, weekly, monthly, and yearly). Please note that this option will be deprecated on January 31, 2023. For more questions or support, please reach out to Adobe Customer Care. [Learn more](/help/analyze/report-builder/r-arb-scheduled-reports.md)|

{style="table-layout:auto"}

## End-of-life notices

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **EOL of [!UICONTROL Publishing Lists] feature** | September 29, 2022 | As part of the EOL of Reports & Analytics, Publishing Lists are slated to reach end-of-life in **December 2023**. You will not be able to create new or access existing Publishing Lists to send or schedule Analysis Workspace projects. [Learn more](/help/admin/admin/publishing-list.md) |
| **EOL for Data Workbench** | September 14, 2022 | Adobe intends to end-of-life Data Workbench effective **December 31, 2023**. See [Data Workbench end-of-life announcement](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) for details. Contact your organization's Adobe Account Manager with any questions. |
| **EOL for [!DNL Reports & Analytics]** | January 4, 2022 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe's technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process. |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.23.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

## Related resources

* [Previous release notes for 2022](/help/release-notes/2022.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
