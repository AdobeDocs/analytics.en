---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (February 2023)

**Last update**: February 27, 2023

Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features in Adobe Analytics

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| Data Dictionary | The Data Dictionary in Analysis Workspace helps both users and administrators keep track of and better understand the components in their Analytics environment. Learn more | March 8, 2023 | March 22, 2023 |
| Secure Destinations for data export in Analytics Data Feeds | TBD | N/A | March 8, 2023 |
| Sequential Data Stories in Mobile Dashboards | TBD | N/A | March 8, 2023 |

## Fixes in Adobe Analytics

To follow

## Important notices for Adobe Analytics administrators

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **Update to device lookups due to Google Client Hints** | February 27, 2023 | The use of client hints, planned for February 16, 2023, was postponed in order to better ensure the quality of device lookups using hints. We proceeded with the first phase of the release for support of Client Hints on February 27, 2023. The second and final phase of the release was completed on Thursday, March 2, 2023. [Learn more](/help/technotes/client-hints.md)|
| **Analytics Source Connector availability** | February 15, 2023 | On February 28, 2023, the Analytics Source Connector was made available in the new Adobe Experience Platform data center located in Canada. |
| **Automatic migration to Classification Set architecture** | February 8, 2023 | Over the next several months, Adobe plans to migrate all classifications across all organizations to the latest classification architecture. The last customers to migrate is estimated to happen in May 2023. No customer action is required, and no down time is expected. This new architecture has many benefits, including:<ul><li>Significantly reduced processing time (72 hours → 24 hours)</li><li>The ability to use the [Classification Sets](/help/components/classifications/sets/overview.md) UI</li><li>The option to use classification data in Adobe Experience Platform in the future through the [Adobe Analytics source connector for classification data](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Note the following changes that can potentially impact your organization's workflow:<ul><li>When using the browser or FTP import, '[!UICONTROL Overwrite on conflict]' is always enabled.</li><li>When using the browser or FTP import, the option to export immediately after import is no longer supported.</li><li>The Analytics 2.0 API `GetDimensions` endpoint now returns string identifiers for classifications instead of numeric identifiers. Numeric identifiers can still be used, but Adobe recommends using the new string identifiers where possible. Numeric identifiers can be retrieved by using the `?expansion=hidden` query string parameter.</li></ul>Contact Adobe Customer Care if you want a more specific migration schedule for your organization, or have questions/concerns around this migration. [Learn more](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## End-of-life (EOL) notices

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
