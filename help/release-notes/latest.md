---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (April 2023)

**Last update**: April 6, 2023

Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features in Adobe Analytics {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Row/column filtering for Analytics Source Connector streaming** | The Analytics Source Connector in Adobe Experience Platform now allows for filtering of Analytics data which is used to populate profiles in [Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en). Row-level filtering helps reduce the number of events associated with profiles. Column-level filtering helps reduce the richness of the events themselves, thus enabling you to optimize the use of profile entitlements. This filtering applies only to data sent to Real-Time Customer Profile and [Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en). **Filtering does not impact the data which is sent to Data Lake for use in applications such as Customer Journey Analytics**. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | N/A | March 29, 2023 |
| **Partial support for Activity Map with Web SDK** | Starting with Web SDK version 2.15.0, we started populating Activity Map data when link tracking is enabled. This allows Web SDK users to get Activity Map reporting if they have link tracking enabled with the Web SDK and Activity Map configured in Analytics.<p>Enabling link tracking with Web SDK currently sends link events when a customer navigates from one page to the next. This is different from how AppMeasurement works and can potentially result in extra billable hits sent to Adobe. Learn more [here](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html) and [here](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)| N/A | March 31, 2023 |
| **IP obfuscation for Experience Edge** | Experience Edge will support IP obfuscation for data sent directly to Adobe Experience Platform. This benefits customers who send data directly to Platform for use in CJA or other Platform solutions. IP obfuscation will be configured at the data stream level. It supports removing the last octet or the whole IP address. **Note**: Obfuscation will NOT apply to data sent to Adobe Analytics. Analytics will continue to get the full IP. IP processing will continue to be done in Analytics separately. In the future, we plan on allowing Analytics data to be obfuscated at the Edge. | N/A | AEP release on April 26, 2023 |
| **Data Dictionary in Analysis Workspace** | The Data Dictionary helps both users and administrators keep track of, manage, and better understand the components (dimensions, metrics) in their Analytics environment. [Learn more](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | March 15, 2023 | **Temporarily unavailable** |
| **Link sharing for projects (no login required)** - Private beta access only | <p>You can now share read-only links to Analysis Workspace projects with people who don't have access to Adobe Analytics. You can share project links with people outside of your organization, or those within your organization who are not provisioned for Adobe Analytics. [Learn more](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>To join the private beta, contact your Adobe Account Team.</p> | April 26, 2023 | June 2023 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed an issue with Operating System.tsv lookup files in Data Feed.
* Fixed an issue with metric values differing between Reports & Analytics and Workspace (AN-315965).
* Fixed an issue with being unable to import partial classifications. (AN-315854)
* Fixed an issue with the Analytics API 1.4. (AN-316475)
* Fixed an issue that prevented some customers from getting classifications for the Page dimension via Report Builder and Report & Analytics. (AN-314445)
* Fixed an issue with being unable to transfer alerts. (AN-306457)

### Other fixes

AN-288373; AN-305144; AN-309023; AN-310466; AN-311686; AN-311705; AN-312018; AN-312105; AN-312116; AN-312191; AN-312502; AN-312737; AN-312854; AN-312991; AN-313253; AN-313275; AN-313278; AN-313282; AN-313365; AN-313390; AN-313547; AN-313549; AN-313818; AN-313986; AN-314080; AN-314248; AN-314251; AN-314262; AN-314300; AN-314309; AN-314448; AN-314643; AN-314564; AN-314645; AN-314705; AN-314761; AN-314831; AN-314919; AN-314948; AN-315032; AN-315115; AN-315154; AN-315158; AN-315321; AN-315375; AN-315379; AN-315392; AN-315407; AN-315427; AN-315582; AN-315591; AN-315699; AN-315700; AN-315704; AN-315705; AN-315777; AN-315923; AN-316237; AN-316243; AN-316324; AN-316415; AN-316474; AN-316493; AN-316596; AN-316864; 

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **Device lookup processes now use a third party for all device lookups** | March 3, 2023 |On March 2, 2023, as part of the support rollout for client hints, we updated our device lookup processes to use a third party for all device lookups. Previously, we had used the third party only for mobile device lookups. As part of that rollout, some desktop operating systems were incorrectly labelled with the text "mobile" (e.g. "Mobile OS X 10.15.7" instead of "OS X 10.15.7 ").<p>During Adobe's April release we will correct these names. Analytics and CJA reporting will be updated retroactively, since their reporting looks up operating system name based on an ID which is recorded as part of the event data. Once the lookup value corresponding to an ID is updated, all reporting will be corrected, including historical data. For [!UICONTROL Data Feeds] customers, the change are retroactive if you are using a similar lookup process at the time of reporting. However, if you store the operating system value in your event data, reporting will be updated going forward only. See [Operating System](/help/components/dimensions/operating-systems.md) for more details. |
| **Update to device lookups due to Google Client Hints** | February 27, 2023 | The use of client hints, planned for February 16, 2023, was postponed in order to better ensure the quality of device lookups using hints. We proceeded with the first phase of the release for support of Client Hints on February 27, 2023. The second and final phase of the release was completed on Thursday, March 2, 2023. [Learn more](/help/technotes/client-hints.md)|
| **Automatic migration to Classification Set architecture** | February 8, 2023 | Over the next several months, Adobe plans to migrate all classifications across all organizations to the latest classification architecture. The last customers to migrate is estimated to happen in May 2023. No customer action is required, and no down time is expected. This new architecture has many benefits, including:<ul><li>Significantly reduced processing time (72 hours → 24 hours)</li><li>The ability to use the [Classification Sets](/help/components/classifications/sets/overview.md) UI</li><li>The option to use classification data in Adobe Experience Platform in the future through the [Adobe Analytics source connector for classification data](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Note the following changes that can potentially impact your organization's workflow:<ul><li>When using the browser or FTP import, '[!UICONTROL Overwrite on conflict]' is always enabled.</li><li>When using the browser or FTP import, the option to export immediately after import is no longer supported.</li><li>The Analytics 2.0 API `GetDimensions` endpoint now returns string identifiers for classifications instead of numeric identifiers. Numeric identifiers can still be used, but Adobe recommends using the new string identifiers where possible. Numeric identifiers can be retrieved by using the `?expansion=hidden` query string parameter.</li></ul>Contact Adobe Customer Care if you want a more specific migration schedule for your organization, or have questions/concerns around this migration. [Learn more](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **EOL of Japanese Feature Phone tracking service** | March 21, 2023 | For our Japanese customers only: At the **end of May 2023**, the Japanese Feature Phone tracking service (mod_ktrack) will be discontinued. We apologize for the inconvenience, but we ask that you uninstall or disable the modules that are installed on your Apache server. See pages 27 and 28 in [this document](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf) for reference. |
| **EOL for [!DNL Reports & Analytics]** | March 7, 2023 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe's technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process.<p>On December 31, 2023, we will terminate many of the associated Reports & Analytics features, including, but not limited to: Scheduled Reports, Data Extracts, and DL Reports. After Dec 31, 2023, any scheduled reports will no longer be sent. In **April 2023**, any reports that were scheduled to expire beyond Dec 31, 2023, will automatically be updated and reverted to expire on Dec 31, 2023. In addition, you can no longer schedule future reports beyond December 31, 2023.|
| **EOL of [!UICONTROL People] metric** | March 9, 2023 | With the deprecation of the [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html), the Device Co-op-related People metric is no longer relevant. On May 8, 2023, we will remove the [!UICONTROL People] metric. At that point, we will redirect its data to the [!UICONTROL Unique Visitor] metric to prevent projects, segments and calculated metrics from breaking.<p>**Note**: The [[!UICONTROL People] metric tied to Cross-Device Analytics](/help/components/metrics/people.md) is not affected by this announcement. |
| **EOL of [!UICONTROL Publishing Lists] feature** | September 29, 2022 | As part of the EOL of Reports & Analytics, [!UICONTROL Publishing Lists] are slated to reach end-of-life in **December 2023**. You will not be able to create new or access existing [!UICONTROL Publishing Lists] to send or schedule [!UICONTROL Analysis Workspace] projects. |
| **EOL for Data Workbench** | September 14, 2022 | Adobe intends to end-of-life Data Workbench effective **December 31, 2023**. See [Data Workbench end-of-life announcement](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) for details. Contact your organization's Adobe Account Manager with any questions. |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.23.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2022](/help/release-notes/2022.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
