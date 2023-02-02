---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes

**Last update**: February 2, 2023

Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features in Adobe Analytics

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Updated user interface for Data Privacy labels**  | The updated interface streamlines the process for creating, managing, and editing data privacy labels for report suite components. [Learn more](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en)| N/A | February 8, 2023 |
| **Comparison date ranges in Mobile Scorecards** |  With Mobile Scorecards, you can toggle the **[!UICONTROL Include comparison dates]** setting to view or hide comparison dates. | N/A/ | February 8, 2023 |
| **Calendar updates in Workspace** |<ul><li>Anchor Panel Dates: You can make the date range components relative to the panel calendar. [Learn more](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>Calendar styling updates: The calendar styles throughout the UI have been upgraded to present a more consistent and easy-to-use workflow.</li><li>Calendar formula updates: If you use relative dates, all calendar formulas will reflect the start of the panel date range. [Learn more](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates) | N/A |  February 8, 2023 |
| **Row/column filtering for Adobe Analytics Source Connector streaming** | The Analytics Source Connector in Adobe Experience Platform will been enhanced to allow filtering of Analytics data which is used to populate profiles in [Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en). Row-level filtering helps reduce the number of events associated with profiles. Column level-filtering helps reduce the richness of the events themselves, thus enabling you to optimize the use of profile entitlements. This filtering applies only to data sent to Unified Profile and Unified Identity Services. **Filtering does not impact the data which is sent to Data Lake for use in applications such as Customer Journey Analytics**. | N/A | February 22, 2023 |

## Fixes in Adobe Analytics

TBD

## Important notices for Adobe Analytics administrators

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **Update to device lookups due to Google Client Hints** | January 25, 2023 | The use of client hints in device lookup will start on **February 16, 2023**. <p> <p>As of October 2022, it is possible to collect client hints with either the Web SDK or AppMeasurement JavaScript libraries. But client hints will not be incorporated into device lookup until February 2023. At that time, Adobe will begin using client hints in addition to the User-Agent when deriving certain device information for hits coming from Chromium browsers, such as Google Chrome and Microsoft Edge. This is in response to Google's plan to gradually reduce the information presented from the User-Agent string in lieu of data passed via client hints. <p> <p>As part of this change, Adobe will use Device Atlas for all device lookups related to User-Agent. [Learn more](/help/technotes/client-hints.md)|
| **Pausing scheduled reports in Reports & Analytics** | January 6, 2023 | Adobe deprecated these features on **Jan 31, 2023**. Please note that expiration windows for both reports and data extracts will continue to be limited to nine months; report and data extract delivery will pause at the end of this period unless the schedule is reactivated.<p>Before January 31, 2023, you had to migrate your scheduled reporting to one of the other mechanisms available to you in Adobe Analytics. For additional questions or support, please reach out to Adobe Customer Care. [Learn more](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausing scheduled tasks in Report Builder** | January 6, 2023 | On **January 31, 2023**, Adobe rolled out changes to scheduled tasks in Report Builder as part of our performance and delivery optimization efforts. These changes included removing the ability to have scheduled deliveries "end after x occurrences."<p>You can continue to schedule hourly Report Builder tasks and have them end after a maximum of 99 occurrences. Please note that the rollback only applies to hourly tasks; the "end after x occurrences" will remain unavailable for all other delivery intervals (daily, weekly, monthly, and yearly). For more questions or support, please reach out to Adobe Customer Care. [Learn more](/help/analyze/report-builder/r-arb-scheduled-reports.md)|

## End-of-life notices

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **EOL of [!UICONTROL Publishing Lists] feature** | September 29, 2022 | As part of the EOL of Reports & Analytics, Publishing Lists are slated to reach end-of-life in **December 2023**. You will not be able to create new or access existing Publishing Lists to send or schedule Analysis Workspace projects. |
| **EOL for Data Workbench** | September 14, 2022 | Adobe intends to end-of-life Data Workbench effective **December 31, 2023**. See [Data Workbench end-of-life announcement](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) for details. Contact your organization's Adobe Account Manager with any questions. |
| **EOL for [!DNL Reports & Analytics]** | January 4, 2022 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe's technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process. |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.23.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2022](/help/release-notes/2022.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
