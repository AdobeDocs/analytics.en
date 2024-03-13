---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (March 2024)

**Last update**: March 13, 2024

These release notes cover the release period of March 12, 2024 through April 2024. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AppMeasurement update** | [AppMeasurement release v2.26.0](/help/implement/appmeasurement-updates.md) is available. | | March 4, 2024 |
| **New column available on the Projects landing page** | The **[!UICONTROL Last used]** column is now available when viewing the Projects tab on the [Adobe Analytics landing page](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html). This information can help you determine whether a project is valuable to users in your organization by showing the date and time when the project was last opened. Previously, the **[!UICONTROL Last used]** column was available only in the Calculated metrics manager, Segments manager, and Alerts manager. |  | March 13, 2024 |
| **Analytics support for consent flags required by Google for DMA** | Due to new European privacy regulations, Google requires that data collected in Europe that was sent to them must indicate whether two particular kinds of consent were granted. **Starting March 6th**, Google will no longer accept event data that does not indicate that the relevant consent was granted. Adobe Analytics expects to release support for capturing this data in mid March. We will communicate more details shortly. |  | Mid March, 2024 |
| **Use the same cloud accounts for Data Feeds, Data Warehouse, and Classification sets** | Cloud accounts and locations that you create can now be used for exporting data (with Data Feeds and Data Warehouse) and importing data (with Classification sets).<p> **Changes when configuring accounts:** Users can Configure cloud import and export accounts and Configure cloud import and export locations that can be used for any of the following purposes:<ul><li>Importing data with Classification sets</li><li>Exporting data with Data Feeds</li><li>Exporting data with Data Warehouse.<p> **Changes when managing accounts**: Users can use the Locations page (under Components > Locations) to view and manage all the accounts and locations that they create, regardless of where they were created. Previously, the Locations page applied only to accounts that were created for importing data with Classification sets. | | April 2024 |
| **Administrators can manage all locations in their organization** | A new option on the Locations page allows Administrators to view and manage all locations in the organization. Previously, administrators could view and manage only the locations they created. |  | April 2024 |
| **Activity Map for Web SDK without extra cost** | Currently, Activity Map link events are counted as their own events and incur extra cost. This enhancement takes some link events and packages them into the next hit, similar to how events are handled by AppMeasurement. |  | April 3, 2024 |
| **Increase in default low-traffic thresholds**| In **mid April 2024**, Adobe will begin increasing the default report suite low-traffic thresholds as follows: ![low-traffic thresholds](assets/thresholds.png) This will impact only variables which are currently set below the new thresholds. These changes will be made incrementally, and we expect the work to be complete by the **end of May**. As these increases are rolled out, you may notice changes for high-cardinality variables:<ul><li>More dimension values may be available for reporting.</li><li>Segments and calculated metrics may include more data.</li><li>Virtual report suites based on segments may include more data.</li><li>Classification exports may include more data.</li></ul> | | Mid April, 2024 |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed the following Classifications issues: AN-335632; AN-337559; AN-340164; AN-340370; AN-341089; AN-341211; AN-341284; AN-341469; AN-341481; AN-341760; AN-341778; AN-342144; AN-342258; AN-342338, AN-342400
* Fixed the following Classifications Rule Builder issues: AN-340921; AN-341269; AN-341292; AN-341467; AN-341666; AN-342145; AN-342329
* Fixed the following Intelligent Alerts issue: AN-340736
* Fixed the following Segmentation issue: AN-336242
* Fixed the following Data Warehouse issues: AN-335354; AN-339446; AN-339774; AN-340221; AN-340599; AN-341277; AN-342009; AN-342088; AN-342592
* Fixed the following Data Feeds issues: AN-335508; AN-340887; AN-341050; AN-341208; AN-341403; AN-341479; AN-341524; AN-341661; AN-342000; AN-342125; AN-342256; AN-342301; AN-342410; AN-342502; AN-342525
* Fixed the following Report Builder issue: AN-340540
* Fixed the following Analysis Workspace issues: AN-295889; AN-330981; AN-338818; AN-339730; AN-341114; AN-341520; 

### Other Analytics fixes

AN-312198; AN-338009; AN-339549; AN-333970; AN-334790; AN-336461; AN-336572; AN-339549; AN-341119; AN-341246; AN-341268; AN-341272; AN-341475; AN-341547; AN-341558; AN-341680; AN-342017; 

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **Adobe API object member additions** | January 17, 2024 | Adobe may add optional request and response members (name/value pairs) to existing API objects at any time and without notice or changes in versioning. Adobe recommends that you refer to the API documentation of any third-party tool you integrate with our APIs so that such additions are ignored in processing, if not understood. If implemented properly, such additions are non-breaking changes for your implementation. Adobe will not remove parameters or add required parameters without first providing standard notification through release notes. |
| **`getPageLoadTime` plugin deprecated** | January 10, 2024 | This plugin is no longer supported. Its code utilizes the performance.timing method, which (according to MDN) has been [deprecated](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). Work on an updated plugin has started. |

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.26.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2023](/help/release-notes/2023.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
