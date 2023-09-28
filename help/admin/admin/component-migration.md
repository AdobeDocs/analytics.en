---
description: Explains how to migrate components and projects from Adobe Analytics to Customer Journey Analytics.
title: Migrate components and projects from Adobe Analytics to Customer Journey Analytics
feature: Admin Tools
---
# Migrate components and projects from Adobe Analytics to Customer Journey Analytics

Adobe Analytics administrators can migrate Adobe Analytics components and projects to Customer Journey Analytics. 

The migration process includes:

* Re-creating Adobe Analytics projects in Customer Journey Analytics.

* Matching dimensions and metrics from Adobe Analytics report suites to dimensions and metrics in Customer Journey Analytics data views. 

  Some dimensions and metrics are automatically matched; others you must manually match as part of the migration process.

## Prepare for a migration

### Prerequisites

Before your projects and their associated dimensions and metrics are ready to migrate, you first need to:

* Use the Analytics source connector to view Adobe Analytics report suite data in Customer Journey Analytics. To do that, you need to:

  * [Set up report suites for ingestion into Adobe Experience Platform and Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

  * [Ingest and use the data](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html)

* Ensure that users in Customer Journey Analytics are provisioned to the data views where data is being matched. 

  For more information, see [Customer Journey Analytics permissions in the Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Customer Journey Analytics access control](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  The Permissions tab is part of each product profile in Admin Console. You can add users to specific product profiles. Then you assign rights to specific data views and specify which permissions the users in a product profile have. 

* Create a migration plan, as described in the section below, [Create a migration plan as an organization](#create-a-migration-plan-as-an-organization).

### Understand what is included in a migration

The following table outlines which elements of a project and component are included in a migration:


|  | Projects | Dimensions and metrics |
|---------|----------|---------|
| **Date ranges** | Yes | N/A |
| **Segments** | Yes | N/A |
| **Quick segments** | Yes | N/A |
| **Panels** | Yes | N/A |
| **Visualizations** | Yes | N/A |
| **Owner** | (Defined by user doing the migration) | ? |
| **Curation** | No | N/A |
| **Sharing (project roles)** | No | No |
| **Annotations** | No | N/A |
| **Folder structure** | No | N/A |
| **Descriptions** | Yes | ? |
| **Tags** | ? | ? |
| **Schedules** | ? | N/A |
| **Attribution (on dimensions)** | N/A | ? |
| **Anomaly Detection** | ? | N/A |
| **Contribution Analysis** | ? | N/A |
| **Alerts** | ? | N/A |

{style="table-layout:auto"}

### Create a migration plan as an organization

Because any components that are matched for a given project migration apply to any future project migrations for the entire organization, it's important that your organization plans all project migrations in advance. 

You should decide as an organization which dimensions and metrics will be matched what gets matched with what, in order to avoid individual administrators making decisions in a silo at the time of a project's migration.

## Migrate Adobe Analytics projects to Customer Journey Analytics

>[!IMPORTANT]
>
>Before you migrate any projects to Customer Journey Analytics as described in this section, learn more about migrating projects in the [Plan the migration](#plan-the-migration) section above. 
>
>Any dimensions or metrics you match are permanent, both for this project and for all future projects that are migrated throughout your entire organization. Any matches that you make cannot be modified.



1. In Adobe Analytics select the [!UICONTROL **Admin**] tab, then select [!UICONTROL **All admin**].

1. Under [!UICONTROL **Data configuration & collection**], select [!UICONTROL **Component migration**].

1. (Conditional) To quickly find the project that you want to migrate, you can either:

   * Filter the list of projects by selecting the Filter icon. 

     You can filter by the following criteria:

     * Status

     * Tags

     * Report suite

     * Owners

     * Other filters

   * Use the search field to search for the project you want to migrate. 

1. Mouse over the project that you want to migrate, then select the **Migrate** icon ![Migrate project](assets/migrate.svg).

   Or

   Select the project that you want to migrate, then select [!UICONTROL **Migrate to Customer Journey Analytics**].

   You can select only one project at a time to migrate.

   The [!UICONTROL **Migrate project_name to Customer Journey Analytics**] dialog box is displayed.

   <!-- add screenshot -->
   
1. In the [!UICONTROL **Project owner**] field, begin typing the name of the user who you want to set as the owner of the project in Customer Journey Analytics, then select their name in the drop-down menu. 

   The owner that you specify has full management rights to the project. 

1. In the [!UICONTROL **Match schema for report suites**] section, select a report suite.

1. In the [!UICONTROL **Data view**] drop-down menu, select the Customer Journey Analytics data view where you want the the project and components to be migrated.  

1. Select [!UICONTROL **Match schema**].

1. In the [!UICONTROL **Match schema**] section, expand the [!UICONTROL **Dimensions**] and [!UICONTROL **Metrics**] sections. 

   Some dimensions and metrics in Adobe Analytics are automatically matched to a dimension or metric in Customer Journey Analytics. Others need to be manually matched.

   **Automatically matched dimensions and metrics**

   Some dimensions and metrics in Adobe Analytics are automatically matched to a dimension or metric in Customer Journey Analytics. You can't make any matching decisions for these dimensions and metrics.
   
   For example, the **Visits** metric in Adobe Analytics is automatically matched with the **Sessions** metric in Customer Journey Analytics.

   You can select any dimension or metric to view their associated IDs. 

   <!-- update screenshot after I can see the Status column -->

   ![Project migration schema](assets/project-migration-schema.png)

   **Manually match dimensions and metrics**
   
   Other dimensions and metrics in Adobe Analytics cannot be automatically matched to a dimension or metric in Customer Journey Analytics. 

   When a dimension or metric cannot be automatically matched, an orange counter displays next to the [!UICONTROL **Dimensions**] or [!UICONTROL **Metrics**] section header, indicating the number of dimensions or metrics that need to be manually matched. In the table, a warning icon ![warning icon](assets/schema-warning.png) displays next to each dimension or metric that needs to be manually matched.

   <!-- update screenshot after I can see the Status column -->

   ![Migration schema manual match](assets/schema-manual-map.png)

1. To manually match dimensions and metrics, select a dimension or metric that contains a warning icon ![warning icon](assets/schema-warning.png), then in the [!UICONTROL **Matching Customer Journey Analytics metric**] field (or the [!UICONTROL **Matching Customer Journey Analytics dimension**] field if you are matching a dimension), select the dimension or metric in Customer Journey Analytics that you want to match with the dimension or metric you selected.

   ![match dimensions and metrics](assets/schema-manual-map-drop-down.png)

   Repeat this process for each dimension or metric that contains the warning icon.
   
   After all dimensions and metrics in the Adobe Analytics report suite are matched to a dimension or metric in the Customer Journey Analytics data view, a green check mark ![check mark](assets/report-suite-check.png) appears next to the report suite name in the [!UICONTROL **Match schema for report suites**] section.

1. (Conditional) If the project you are migrating contains more than one report suite, select another report suite in the [!UICONTROL **Match schema for report suites**] section, then repeat step 6 through Step 10. <!-- double-check that the step numbers are still correct -->

1. Select [!UICONTROL **Migrate**].

   >[!WARNING]
   >
   >   An on-screen warning message displays after you select [!UICONTROL **Migrate**]. Before you choose to continue, understand that any dimensions or metrics you match are permanent, both for this project and for all future projects that are migrated throughout your entire organization. If you continue, the matches you make cannot be modified.
