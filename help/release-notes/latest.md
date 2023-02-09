---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (February 2023)

**Last update**: February 9, 2023

Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features in Adobe Analytics

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Updated user interface for Data Privacy labels**  | The updated interface streamlines the process of creating, managing, and editing data privacy labels for report suite components. [Learn more](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en)| N/A | February 8, 2023 |
| **Hide comparison date ranges in Mobile Scorecards** |  With Mobile Scorecards, you can toggle the **[!UICONTROL Include comparison dates]** setting to view or hide comparison dates. | N/A | February 8, 2023 |
| **Calendar updates in Workspace** |<ul><li>Anchor Panel Dates: You can make the date range components relative to the panel calendar. [Learn more](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>Calendar styling updates: The calendar styles throughout the UI have been upgraded to present a more consistent and easy-to-use workflow.</li><li>Calendar formula updates: If you use relative dates, all calendar formulas will reflect the start of the panel date range. [Learn more](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | N/A |  February 8, 2023 |
| **Row/column filtering for Adobe Analytics Source Connector streaming** | The Analytics Source Connector in Adobe Experience Platform now allows for filtering of Analytics data which is used to populate profiles in [Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en). Row-level filtering helps reduce the number of events associated with profiles. Column level-filtering helps reduce the richness of the events themselves, thus enabling you to optimize the use of profile entitlements. This filtering applies only to data sent to Real-Time Customer Profile and [Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en). **Filtering does not impact the data which is sent to Data Lake for use in applications such as Customer Journey Analytics**. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | N/A | February 22, 2023 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

AN-302282; AN-303127; AN-303541; AN-303550; AN-305282; AN-306504; AN-307351; AN-307496; AN-307530; AN-307947; AN-308497; AN-308610; AN-308777; AN-308994; AN-309143; AN-309404; AN-309414; AN-309445; AN-309575; AN-309630; AN-309658; AN-309690; AN-309742; AN-309861; AN-309967; AN-309973; AN-310059; AN-310132; AN-310168; AN-310238; AN-310241; AN-310301; AN-310318; AN-310324; AN-310335; AN-310338; AN-310460; AN-310500; AN-310684; AN-310690; AN-311010; AN-311022; AN-311043; AN-311125; AN-311250; AN-311370; AN-311458; 

## Important notices for Adobe Analytics administrators

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **Automatic migration to Classification Set architecture** | February 8, 2023 | Over the next several months, Adobe plans to migrate all classifications across all organizations to the latest classification architecture. The last customers to migrate is estimated to happen in May 2023. No customer action is required, and no down time is expected. This new architecture has many benefits, including:<ul><li>Significantly reduced processing time (72 hours → 24 hours)</li><li>The ability to use the [Classification Sets](/help/components/classifications/sets/overview.md) UI</li><li>The option to use classification data in Adobe Experience Platform in the future through the [Adobe Analytics source connector for classification data](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Note the following changes that can potentially impact your organization's workflow:<ul><li>When using the browser import, '[!UICONTROL Overwrite on conflict]' is always enabled.</li><li>When using the browser import, the option to export immediately after import is no longer supported.</li><li>The Analytics 2.0 API `GetDimensions` endpoint now returns string identifiers for classifications instead of numeric identifiers. Numeric identifiers can still be used, but Adobe recommends using the new string identifiers where possible. Numeric identifiers can be retrieved by using the `?expansion=hidden` query string parameter.</li></ul>Contact Adobe Customer Care if you want a more specific migration schedule for your organization, or have questions/concerns around this migration. [Learn more](/help/components/classifications/sets/overview.md) |
| **Update to device lookups due to Google Client Hints** | January 25, 2023 | The use of client hints in device lookup will start on **February 16, 2023**. <p> <p>As of October 2022, it is possible to collect client hints with either the Web SDK or AppMeasurement JavaScript libraries. But client hints will not be incorporated into device lookup until February 2023. At that time, Adobe will begin using client hints in addition to the User-Agent when deriving certain device information for hits coming from Chromium browsers, such as Google Chrome and Microsoft Edge. This is in response to Google's plan to gradually reduce the information presented from the User-Agent string in lieu of data passed via client hints. <p> <p>As part of this change, Adobe will use Device Atlas for all device lookups related to User-Agent. [Learn more](/help/technotes/client-hints.md)|

{style="table-layout:auto"}

## End-of-life (EOL) notices

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **EOL of some Reports & Analytics and Report Builder scheduling features** | February 9, 2023 | The following scheduling features were end-of-lifed on January 31, 2023:<ul><li>The "end after x occurrences" option for hourly tasks in Report Builder</li><li>The ability to schedule new reports and download data extracts in Reports and Analytics</li></ul><p>**Note**: We originally terminated these features in April 2022 but rolled back the change. We also sent a notification that these features were being temporarily restored and that they would be re-terminated on Jan 31, 2023. |
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
