---
title: Current Adobe Analytics release notes
description: View the current Adobe Analytics release notes
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
---
# Current Adobe Analytics release notes (June 2024)

**Last update**: June 26, 2024

These release notes cover the release period of June 12, 2024 through July. Adobe Analytics releases operate on a [continuous delivery model](releases.md) which allows for a more scalable, phased approach to feature deployment. Accordingly, these release notes get updated several times a month. Please check them regularly.

## New features or enhancements {#features}

| Feature | Description | [Rollout starts](releases.md) | [General Availability](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Select multiple fields in a drop-down filter** |  When multiple fields have been added to a drop-down filter, users can now select more than one field at a time. The panel is filtered to include any of the selected fields. <p>Previously, users could select only one field at a time in a drop-dow filter.</p><p>For more information, see [Static drop-down segments](/help/analyze/analysis-workspace/c-panels/panels.md#static-drop-down-segments) in [Panels overview](/help/analyze/analysis-workspace/c-panels/panels.md).</p><p>[View a video demonstration of this feature](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/use-multi-select-drop-down-filters).</p> |  | June 19, 2024 |
| **Table of contents for Workspace projects** | A new table of contents is now available for projects. The table of contents provides links that enable users to quickly jump to panels and visualizations within the project. The table of contents can be enabled for individual projects or for all projects for a given user.<p>For more information, see [Project table of contents](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md).</p><p>[View a video demonstration of this feature](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/create-a-toc-in-analysis-workspace).</p> |  | June 19, 2024 |
| **Create hyperlinks for dimension items in a freeform table** |You can create hyperlinks for one or more dimension items to make them clickable within a freeform table in Analysis Workspace. <p>You can create hyperlinks for dimension items that have URL values, or you can create custom URLs for dimension items that have non-URL values.</p><p>You can create dynamic custom URLs for multiple dimension items by using variables. Variables can reference the value of a dimension item or they can reference the breakdown dimension.</p><p>For more information, see [Create hyperlinks for dimensions in a freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).</p><p>[View a video demonstration of this feature](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/tips-and-tricks/create-hyperlinks-in-freeform-tables).</p> |  | June 19, 2024 |
| **Administrator settings to control the accounts and locations that are used for export and import** | A new ["Admin settings" tab in the Locations manager](/help/components/locations/locations-manager.md#configure-company-wide-settings-administrators-only) gives administrators control over whether users can create and edit accounts and locations. These settings apply when users [configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [configure cloud import and export locations](/help/components/locations/configure-import-locations.md). <p>Administrators can also limit the types of accounts (Google Cloud Platform, Azure RBAC, Amazon S3, and so forth) that users can create and use.</p><p>Previously, any user could create, edit, and use accounts and locations for any type of account.</p> |  June 12, 2024 | June 20, 2024 |
| **Share accounts and locations that are used for export and import** | Users can now make the accounts and locations they create available to all users in their organization. Only account and location owners and system administrators can edit and delete accounts and locations.<p>Previously, accounts and locations could be used only by the user who created them.</p><p>These settings are available when users [configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts) and [configure cloud import and export locations](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations). </p>  | June 12, 2024 | June 20, 2024 |
| **Activity Map to use fewer server calls for Web SDK** | Currently, Activity Map link events are counted as their own events and incur extra cost. This enhancement takes some link events and packages them into the next hit, similar to how events are handled by AppMeasurement. <p>(Updated documentation link to follow)</p> | Open Beta starts July 10, 2024 | TBD |
| **New Data Sources API Guide** | The [Adobe Analytics 2.0 Data Sources API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-sources/) endpoints provide methods to create, view, delete, and upload to Data Sources accounts. |  | Available now |
| **New methods in the Classifications API Guide** | Two new methods for retrieving file partitions were added to the Classifications API Guide.<ul><li>[Get classification job file partition](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/#get-classification-job-file-partition-list)</li><li>[Get classification export job file part](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/#get-classification-export-job-file-part)</li></ul> |  | Available now |

{style="table-layout:auto"}

## Fixes in Adobe Analytics

* Fixed the following Classifications issues: AN-347682; AN-348396; AN-348625; AN-348668; AN-348926; AN-348936; AN-349040; AN-349191; AN-349195; AN-349443; AN-349697; AN-349758; AN-349862; AN-350051; AN-350054; AN-350208; AN-350497; AN-350525; AN-351067
* Fixed the following Data Warehouse issues: AN-346862; AN-349409; AN-349926; AN-350629; AN-350996
* Fixed the following Data Feeds issues: AN-346727; AN-348282; AN-348334; AN-348725; AN-348726; AN-348823; AN-349081; AN-349207; AN-349307; AN-349539; AN-349710; AN-349729; AN-349742; AN-349878; AN-349943; AN-350527; 
* Fixed the following Data Sources issue: AN-350038
* Fixed the following Analysis Workspace issues: AN-342953; AN-346346; AN-349590; AN-349717; AN-350057; AN-350697; AN-350904
* Fixed the following Report Builder issues: AN-348903; AN-350691
* Fixed the following A4T issues: AN-347690; AN-350853

### Other Analytics fixes

AN-346470; AN-346850; AN-347227; AN-348145; AN-348564; AN-349001; AN-349008; AN-349211; AN-349719; AN-350523;

## Important notices for Adobe Analytics administrators {#admin}

| Notice | Date Added or Updated  | Description |
| ----------- | ---------- | ---------- |
| **13-month expiration of saved `cust_visids`**  | May 22, 2024 | An upcoming release of the Analytics Hit processing engine, **targeted for July 2024**, will start enforcing a 13-month expiration of saved `cust_visids`. If the report suite has "Enable Visitor Stitching" enabled, this setting is used for finding the `cust_visid` for a `visid_high/visid_low value` with no `cust_visid` on the hit. Currently, there is no expiration of the mapping of a `cust_visid` for a `visid_high/visid_low`. With this release, if 13 months or more have passed since `visid_high/visid_low` has had a `cust_visid` on a hit, the mapping expires. | 
| **ISO region updates** | May 10, 2024 | Adobe will perform 2024 ISO region updates on June 7, 2024. Expect to see minor geo information (region) updates following this release. |

{style="table-layout:auto"}

## End-of-life (EOL) notices {#eol}

| EOL Product or Feature | Date added or updated | Description |
| --- | --- | --- |
| **Migration to Adobe I/O OAuth Server-to-Server credentials** | May 11, 2023 |  Adobe Analytics API and Livestream customers using Adobe I/O JWT credentials must migrate to Adobe I/O OAuth Server-to-Server credentials by **January 1, 2025**. Adobe I/O will not allow new JWT credentials to be created beginning May 1, 2024. Customers using JWT must create a new OAuth Server-to-Server credential or migrate their existing JWT credential to an OAuth Server-to-Server credential. Customers must also update their client applications to use the new OAuth Server-to-Server credentials. <ul><li>[Migrating from Service Account (JWT) credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementation guide for new and old applications with OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Using the new OAuth Server-to-Server credentials](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQs](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

For the latest updates on AppMeasurement releases (Version 2.26.0), please refer to [AppMeasurement for JavaScript release notes](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Related resources

* [Previous release notes for 2024](/help/release-notes/2024.md)
* [Customer Journey Analytics release notes](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Media Analytics release notes](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* The latest release updates for [Adobe Experience Cloud products](https://business.adobe.com/products/adobe-experience-cloud-products.html)
