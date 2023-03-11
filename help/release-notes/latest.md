---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (March 2023)

**Last update**: March 9, 2023

Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features in Adobe Analytics {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Data Dictionary in Analysis Workspace** | The Data Dictionary helps both users and administrators keep track of, manage, and better understand the components (dimensions, metrics) in their Analytics environment. [Learn more](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | March 15, 2023 | March 22, 2023 |
| **Data Stories in Mobile Dashboards** | Data stories let you add multiple customizable detail views to tiles in Mobile Scorecard projects. Use data stories to dive deeper into key drivers, related metrics, and different steps along the customer journey. You can easily swipe through these views to understand the whole story behind your key metrics. [Learn more](/help/analyze/mobile-app/create-scorecard.md#create-data-story)  | N/A | March 8, 2023 |
| **Expiration dates for scheduled project** | You can set maximum expiration dates for scheduled projects to up to one year, regardless of schedule frequency. | N/A | March 8, 2023 |
| **Link sharing for projects (no login required)** - Private beta access only | <p>You can now share read-only links to Analysis Workspace projects with people who don't have access to Adobe Analytics. You can share project links with people outside of your organization, or those within your organization who are not provisioned for Adobe Analytics. [Learn more](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>To join the private beta, contact your Adobe Account Team.</p> | March 15, 2023 (Private beta) | April 2023 |
| **Panel date range updates** |  In Workspace, we added the following improvements:<ul><li>Starting with the February release, dimension items and data previews will be based on the panel date range and not the last 90 days. </li><li>All dimension items listed will based on having data within panel date range. If a dimension item has data outside the date range, users can show more beyond the date range at the bottom of the list.</li><li>•	Any dimension that does not have data will still be displayed in the left rail, but there will be do dimension items and users will need to click on the show more options to view dimension items with data outside the panel date range.</li><li>All date previews in the segment and calculated metric builders will be based on the panel date range (unless accessed from the component managers, which do not have an associated panel, they will still be based on the last 90 days).</li><li>previews will display data or components based on the panel date range.</li></ul>| N/A | February 8, 2023 |

## Fixes in Adobe Analytics

AN-308177; AN-308727; AN-308846; AN-309591; AN-310614; AN-311544; AN-311570; AN-311665; AN-311948; AN-312108; AN-312114; AN-312142; AN-312143; AN-312389; AN-312391; AN-312431; AN-312453; AN-312454; AN-312458; AN-312503; AN-312533; AN-312682; AN-312698; AN-312714; AN-312738; AN-312807; AN-312829; AN-312849; AN-312875; AN-312980; AN-312997; AN-313059; AN-313077; AN-313110; AN-313195; AN-313196; AN-313258; AN-313554; AN-313580; AN-313702; AN-313820; AN-313844; AN-313859; AN-313879; AN-314273

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **Update to device lookups due to Google Client Hints** | February 27, 2023 | The use of client hints, planned for February 16, 2023, was postponed in order to better ensure the quality of device lookups using hints. We proceeded with the first phase of the release for support of Client Hints on February 27, 2023. The second and final phase of the release was completed on Thursday, March 2, 2023. [Learn more](/help/technotes/client-hints.md)|
| **Analytics Source Connector availability** | February 15, 2023 | On February 28, 2023, the Analytics Source Connector was made available in the new Adobe Experience Platform data center located in Canada. |
| **Automatic migration to Classification Set architecture** | February 8, 2023 | Over the next several months, Adobe plans to migrate all classifications across all organizations to the latest classification architecture. The last customers to migrate is estimated to happen in May 2023. No customer action is required, and no down time is expected. This new architecture has many benefits, including:<ul><li>Significantly reduced processing time (72 hours → 24 hours)</li><li>The ability to use the [Classification Sets](/help/components/classifications/sets/overview.md) UI</li><li>The option to use classification data in Adobe Experience Platform in the future through the [Adobe Analytics source connector for classification data](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Note the following changes that can potentially impact your organization's workflow:<ul><li>When using the browser or FTP import, '[!UICONTROL Overwrite on conflict]' is always enabled.</li><li>When using the browser or FTP import, the option to export immediately after import is no longer supported.</li><li>The Analytics 2.0 API `GetDimensions` endpoint now returns string identifiers for classifications instead of numeric identifiers. Numeric identifiers can still be used, but Adobe recommends using the new string identifiers where possible. Numeric identifiers can be retrieved by using the `?expansion=hidden` query string parameter.</li></ul>Contact Adobe Customer Care if you want a more specific migration schedule for your organization, or have questions/concerns around this migration. [Learn more](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **EOL for [!DNL Reports & Analytics]** | March 7, 2023 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe's technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process.<p>On December 31, 2023, we will terminate many of the associated Reports & Analytics features, including, but not limited to: Scheduled Reports, Data Extracts, and DL Reports. After Dec 31, 2023, any scheduled reports will no longer be sent. In **April 2023**, any reports that were scheduled to expire beyond Dec 31, 2023, will automatically be updated and reverted to expire on Dec 31, 2023. In addition, you can no longer schedule future reports beyond December 31, 2023.|
| **EOL of [!UICONTROL People] metric** | March 9, 2023 | With the deprecation of the [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html), the Device Co-op-related People metric is no longer relevant. On May 8, 2023, we will remove the [!UICONTROL People] metric. At that point, we will redirect its data to the [!UICONTROL Unique Visitor] metric to prevent projects, segments and calculated metrics from breaking.<p>**Note**: The [[!UICONTROL People] metric tied to Cross-Device Analytics](/help/components/metrics/people.md) is not affected by this announcement. |
| **EOL of [!UICONTROL Publishing Lists] feature** | September 29, 2022 | As part of the EOL of Reports & Analytics, [!UICONTROL Publishing Lists] are slated to reach end-of-life in **December 2023**. You will not be able to create new or access existing [!UICONTROL Publishing Lists] to send or schedule [!UICONTROL Analysis Workspace] projects. |
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
