---
title: Latest Analytics release notes
description: View the current Adobe Analytics release notes.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (June 2023)

<<<<<<< Updated upstream
**Last update**: May 8, 2023
=======
**Last update**: June 1, 2023
>>>>>>> Stashed changes

Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New or updated features in Adobe Analytics {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
<<<<<<< Updated upstream
| **Backfill for non-production sandboxes** | When creating an Analytics Source Connector data flow in a non-production sandbox,  the backfill in non-production sandboxes will be limited to 3 months. It will remain at 13 months for production sandboxes. | N/A | April 26, 2023 | 
| **Link sharing for projects (no login required)** | You can now share read-only links to Analysis Workspace projects with people who don't have access to Adobe Analytics. This includes sharing with people outside of your organization, or those within your organization who are not provisioned for Adobe Analytics. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link)<p>This functionality is enabled by default and can be disabled by the system administrator. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | May 3, 2023 | June 2023 |
| **Updated Home screen for the Analytics dashboards app (Mobile App)** | The new updated Home screen allows you to view all of your scorecards in one consolidated scorecard list.  If you have access to more than one organization under one login, all scorecards from your organizations will be available in a single list. | N/A | May 10, 2023 | 
| **Sort components in Analysis Workspace** | A new Sort option is now available when viewing components either in the left rail or in the Data Dictionary in Analysis Workspace. You can sort components by Recommended (those most commonly used), Alphabetical, or Categorical (type).<p>Previously, you could only search or filter components. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=en)</p> | N/A | May 10, 2023 | 
| **Delete rows containing dynamic dimensions from a Freeform table** | In a Freeform table in Analysis Workspace, you can now quickly delete specific rows that contain dynamic dimensions using the x icon. When doing so, a "Does not equal" filter rule is automatically applied.<p>Previously, the only way to delete rows that contained dynamic dimensions was to manually create a rule in the Filter dialog. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=en)</p> | N/A | May 10, 2023 |
| **New button to add a visualization within a panel** | A new button is now available at the bottom of each panel in Analysis Workspace, allowing you to quickly add a visualization. <p>Previously, the only methods for adding a visualization to a panel were to drag a visualization from the left rail, duplicate or copy an existing visualization, or create a blank panel. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=en#quick-viz)</p> | N/A | May 10, 2023 |
| **Deep Linking (Mobile App)** | Allows users to send links to scorecards that will lead them directly to the scorecard project in the app. This makes it even easier to share projects and boost engagement from a less technical audience. | TBD | TBD |
=======
| **Delete rows containing dynamic dimensions from a Freeform table** | In a Freeform table in Analysis Workspace, you can now quickly delete specific rows that contain dynamic dimensions using the x icon. When doing so, a "Always exclude items" filter rule is automatically applied.<p>Previously, the only way to delete rows that contained dynamic dimensions was to manually create a rule in the Filter dialog. [Learn more](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | N/A | May 17, 2023 |
| **New button to add a visualization within a panel** | A new button is now available at the bottom of each panel in Analysis Workspace, allowing you to quickly add a visualization. <p>Previously, the only methods for adding a visualization to a panel were to drag a visualization from the left rail, duplicate or copy an existing visualization, or create a blank panel. [Learn more](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | N/A | May 17, 2023 |
| **Deep Linking (Mobile App)** | Allows users to send links to scorecards that will lead them directly to the scorecard project in the app. This makes it even easier to share projects and boost engagement from a less technical audience. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#share-scorecards-using-a-shareable-link) | N/A | May 17, 2023 |
| **Link sharing for projects (no login required)** | You can now share read-only links to Analysis Workspace projects with people who don't have access to Adobe Analytics. This includes sharing with people outside of your organization, or those within your organization who are not provisioned for Adobe Analytics. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link)<p>This functionality is enabled by default and can be disabled by the system administrator. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | May 3, 2023 | June 7, 2023 |
>>>>>>> Stashed changes

{style="table-layout:auto"}

## Fixes in Adobe Analytics



## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
<<<<<<< Updated upstream
| **Notice:  New IPs used by Adobe Analytics Data Feeds and Data Warehouse egress in the London Data Center** | April 27, 2023 |For customers in the London Data Center that have Data Feed requests and/or Data Warehouse reports being delivered to an FTP/SFTP service, the following IP address ranges should be added to your firewall configuration in order to allow access: <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |
| **Device lookup processes now use a third party for all device lookups** | March 3, 2023 |On March 2, 2023, as part of the support rollout for client hints, we updated our device lookup processes to use a third party for all device lookups. Previously, we had used the third party only for mobile device lookups. As part of that rollout, some desktop operating systems were incorrectly labelled with the text "mobile" (e.g. "Mobile OS X 10.15.7" instead of "OS X 10.15.7 ").<p>During Adobe's April release we will correct these names. Analytics and CJA reporting will be updated retroactively, since their reporting looks up operating system name based on an ID which is recorded as part of the event data. Once the lookup value corresponding to an ID is updated, all reporting will be corrected, including historical data. For [!UICONTROL Data Feeds] customers, the change are retroactive if you are using a similar lookup process at the time of reporting. However, if you store the operating system value in your event data, reporting will be updated going forward only. See [Operating System](/help/components/dimensions/operating-systems.md) for more details. |
=======
| **37-month expiration of Purchase IDs and Event IDs (event serialization)**  | May 25,2023 | An upcoming release of the Analytics Hit processing engine, targeted for release in **late June 2023 or early July 2023**, will start enforcing a 37-month expiration of Purchase IDs and Event IDs (event serialization). Currently, Purchase IDs and Event IDs never expire in Adobe Analytics. Once a Purchase ID or Event ID is seen/used, then any future hit, no matter when, will have that purchase or event marked as a duplicate. With the new processing engine release:<ul><li>Purchase IDs and Event IDs always expire after 37 months.</li><li>If it has been 37 months since the Purchase ID or Event ID was seen, it is no longer considered a duplicate purchase or event.</li><li> If you are "reusing" Purchase IDs or Event IDs from more than 37 months ago, they are no longer considered duplicates.</li></ul> |
| **Migration to AdobeIO OAuth Server-to-Server credentials** | May 11, 2023 | Adobe Analytics API and Livestream customers using AdobeIO JWT credentials must migrate to AdobeIO OAuth Server-to-Server credentials by **January 1, 2025**. For more details and timelines, see the end-of-life notice in the table below.|
| **New IPs used by Adobe Analytics Data Feeds and Data Warehouse egress in the London Data Center** | April 27, 2023 | This concerns customers in the London Data Center that have Data Feed requests and/or Data Warehouse reports being delivered to an FTP/SFTP service. The following IP address ranges should be added to your firewall configuration in order to allow access: <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |
>>>>>>> Stashed changes

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
<<<<<<< Updated upstream
| **EOL of Japanese Feature Phone tracking service** | March 21, 2023 | For our Japanese customers only: At the **end of May 2023**, the Japanese Feature Phone tracking service (mod_ktrack) will be discontinued. We apologize for the inconvenience, but we ask that you uninstall or disable the modules that are installed on your Apache server. See pages 27 and 28 in [this document](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf) for reference. |
=======
| **Migration to AdobeIO OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using AdobeIO JWT credentials must migrate to AdobeIO OAuth Server-to-Server credentials by **January 1, 2025**. AdobeIO will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul>![](assets/jwt.png) |
>>>>>>> Stashed changes
| **EOL for [!DNL Reports & Analytics]** | March 7, 2023 | Effective **December 31, 2023**, Adobe intends to discontinue [!DNL Reports & Analytics] and its accompanying reports and features. The reports, visualizations, and underlying technology that power [!DNL Reports & Analytics] no longer meet Adobe's technology standards. Most [!DNL Reports & Analytics] features are available in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Since the release of Analysis Workspace in 2015, [!DNL Reports & Analytics] functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. [This notice](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explains the end-of-life process.<p>On December 31, 2023, we will terminate many of the associated Reports & Analytics features, including, but not limited to: Scheduled Reports, Data Extracts, and DL Reports. After Dec 31, 2023, any scheduled reports will no longer be sent. In **April 2023**, any reports that were scheduled to expire beyond Dec 31, 2023, will automatically be updated and reverted to expire on Dec 31, 2023. In addition, you can no longer schedule future reports beyond December 31, 2023.|
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
