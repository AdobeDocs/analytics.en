---
description: Explains how to migrate components and projects from Adobe Analytics to Customer Journey Analytics.
title: Migrate components and projects from Adobe Analytics to Customer Journey Analytics
feature: Admin Tools
hide: yes
hidefromtoc: yes
---
# Migrate components and projects from Adobe Analytics to Customer Journey Analytics

Adobe Analytics administrators can migrate Adobe Analytics components and projects to Customer Journey Analytics. 

The migration process includes:

* Re-creating Adobe Analytics projects in Customer Journey Analytics.

* Mapping dimensions and metrics from Adobe Analytics report suites to dimensions and metrics in Customer Journey Analytics data views. 

  Some dimensions and metrics are automatically mapped; others you must manually map as part of the migration process.

## Prepare for a migration

Before you begin migrating projects in your organization, complete the prerequisites, learn what is and is not migrated, and create a migration plan for your organization.

### Prerequisites

Before your projects and their associated dimensions and metrics are ready to migrate, you first need to:

* Use the Analytics source connector to view Adobe Analytics report suite data in Customer Journey Analytics. To do that, you need to:

  * [Set up report suites for ingestion into Adobe Experience Platform and Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

  * [Ingest and use the data](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html)

* Ensure that users in Customer Journey Analytics are provisioned to the data views where data is being mapped. 

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

Because any components that are mapped for a given project migration apply to any future project migrations for the entire organization, it's important that your organization plans all project migrations in advance. 

You should decide as an organization how dimensions and metrics will be mapped. Doing so avoids individual administrators making decisions in a silo when considering only a single project.

## Migrate Adobe Analytics projects to Customer Journey Analytics

>[!IMPORTANT]
>
>Before you migrate any projects to Customer Journey Analytics as described in this section, learn more about migrating projects in the [Plan the migration](#plan-the-migration) section above. 
>
>Any dimensions or metrics that you map are permanent, both for this project and for all future projects that are migrated throughout your entire organization. Any mappings that you make cannot be modified after the migration comlpetes.

1. In Adobe Analytics, select the [!UICONTROL **Admin**] tab, then select [!UICONTROL **All admin**].

1. Under [!UICONTROL **Data configuration & collection**], select [!UICONTROL **Component migration**].

1. Locate the project that you want to migrate. You can filter, sort, or search the project list.

   By default, only projects that are shared with you are displayed. To view all projects in your organization, select the **Filter** icon, then expand [!UICONTROL **Other filters**] and select [!UICONTROL **Show all**]. (For more information about filtering, sorting, and searching the project list, see [Filter, sort, and search the list of projects](#filter-sort-and-search-the-list-of-projects).)

1. Mouse over the project that you want to migrate, then select the **Migrate** icon ![Migrate project](assets/migrate.svg).

   Or

   Select the project that you want to migrate, then select [!UICONTROL **Migrate to Customer Journey Analytics**].

   You can select only one project at a time to migrate.

   The [!UICONTROL **Migrate project_name to Customer Journey Analytics**] dialog box is displayed.

   <!-- add screenshot -->
   
1. In the [!UICONTROL **Project owner**] field, begin typing the name of the user who you want to set as the owner of the project in Customer Journey Analytics, then select their name in the drop-down menu. 

   The owner that you specify has full management rights to the project. 

1. In the [!UICONTROL **Map schema for report suites**] section, select a report suite.

1. In the [!UICONTROL **Data view**] drop-down menu, select the Customer Journey Analytics data view where you want the the project and components to be migrated.  

1. Select [!UICONTROL **Map schema**].

1. In the [!UICONTROL **Map schema**] section, expand the [!UICONTROL **Dimensions**] and [!UICONTROL **Metrics**] sections. 

   Some dimensions and metrics in Adobe Analytics are automatically mapped to a dimension or metric in Customer Journey Analytics. Others need to be manually mapped.

   **Automatically map dimensions and metrics**

   Some dimensions and metrics in Adobe Analytics are automatically mapped to a dimension or metric in Customer Journey Analytics. You can't make any mapping decisions for these dimensions and metrics.
   
   For example, the **Visits** metric in Adobe Analytics is automatically mapped with the **Sessions** metric in Customer Journey Analytics.

   You can select any dimension or metric to view their associated IDs. 

   <!-- update screenshot after I can see the Status column -->

   ![Project migration schema](assets/project-migration-schema.png)

   **Manually map dimensions and metrics**
   
   Some dimensions and metrics in Adobe Analytics cannot be automatically mapped to a dimension or metric in Customer Journey Analytics. 

   When a dimension or metric cannot be automatically mapped, an orange counter displays next to the [!UICONTROL **Dimensions**] or [!UICONTROL **Metrics**] section header, indicating the number of dimensions or metrics that need to be manually mapped. In the table, a warning icon ![warning icon](assets/schema-warning.png) displays next to each dimension or metric that needs to be manually mapped.

   In addition, the [!UICONTROL **Status**] column says [!UICONTROL **Not mapped**]. 

   <!-- update screenshot after I can see the Status column -->

   ![Migration schema manual map](assets/schema-manual-map.png)

1. To manually map dimensions and metrics, select a dimension or metric that contains a warning icon ![warning icon](assets/schema-warning.png), then in the [!UICONTROL **Mapped Customer Journey Analytics metric**] field (or the [!UICONTROL **Mapped Customer Journey Analytics dimension**] field if you are mapping a dimension), select the dimension or metric in Customer Journey Analytics that you want to map to the dimension or metric you selected.

   ![map dimensions and metrics](assets/schema-manual-map-drop-down.png)

   After a dimension or metric is mapped, the warning icon disappears and the [!UICONTROL **Status**] column changes to [!UICONTROL **Mapped**] with a green dot. (A status of [!UICONTROL **Mapped**] with a gray dot indicates that the dimension or metric was mapped during a previous migration; any previous mappings cannot be updated.)
   
   Repeat this process for each dimension or metric that contains the warning icon.
   
   After all dimensions and metrics in the Adobe Analytics report suite are mapped to a dimension or metric in the Customer Journey Analytics data view, a green check mark ![check mark](assets/report-suite-check.png) appears next to the report suite name in the [!UICONTROL **Map schema for report suites**] section.

1. (Conditional) If the project you are migrating contains more than one report suite, select another report suite in the [!UICONTROL **Map schema for report suites**] section, then repeat step 6 through Step 10. <!-- double-check that the step numbers are still correct -->

1. Select [!UICONTROL **Migrate**].

   >[!WARNING]
   >
   >   An on-screen warning message displays after you select [!UICONTROL **Migrate**]. Before you choose to continue, understand that any dimensions or metrics you map are permanent, both for this project and for all future projects that are migrated throughout your entire organization. If you continue, the mappings you make cannot be modified.

   After a migration completes, the [!UICONTROL **Migration status**] page provides a summary of what was migrated.

   If the migration fails, see the [Retry a failed migration](#retry-a-failed-migration) section below for more information.

## Retry a failed migration

If a migration fails, you can retry the migration.

You can retry a failed migration in either of the following ways:

>[!NOTE]
>
>If the migration continues to fail after retrying, contact Customer Care with the project ID. You can find the project ID on the Migration status page. <!-- when does this page display? How can they get there -->

1. In Adobe Analytics, select the [!UICONTROL **Admin**] tab, then select [!UICONTROL **All admin**].

1. Under [!UICONTROL **Data configuration & collection**], select [!UICONTROL **Component migration**].

1. Select [!UICONTROL **Failed**] in the [!UICONTROL **Migration status**] column next to the project that you want to retry. 

   ![migration status column failed](assets/migration-failed.png) 

   The [!UICONTROL **Migration status**] page displays.
   
   This page also displays immediately after completing the migration steps described in the section [Migrate Adobe Analytics projects to Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) above. 

1. Select [!UICONTROL **Retry migration**].

## Filter, sort, and search the list of projects

You can filter, sort, and search the list of projects on the Component migration page. 

### Filter the list of projects

   You can filter by the following criteria:

   |Filter | Description |
   |---------|----------|
   | [!UICONTROL **Status**] | The status of the migration: <ul><li>[!UICONTROL **Not started**]</li><li>[!UICONTROL **Started**]</li><li>[!UICONTROL **Completed**]</li><li>[!UICONTROL **Failed**]</li></ul>. | 
   | [!UICONTROL **Tags**] | Select any tags in the list of tags. Only projects that have the selected tags applied are displayed. | 
   | [!UICONTROL **Report suite**] | Select any report suite in the list of report suites. Only projects that use the selected report suites are displayed. |
   | [!UICONTROL **Owners**] | Select any owner in the list of owners. Only projects that are owned by the users you select are displayed. |
   | [!UICONTROL **Other filters**] | The following additional filters are available: <ul><li>[!UICONTROL **Mine**]: Shows only projects where you are set as the owner.</li><li>[!UICONTROL **Shared with me**]: Shows only projects that have been shared with you.</li><li>[!UICONTROL **Favorites**]: Shows only projects that are marked as a favorite. (You can mark a project as a favorite from the [project landing page](/help/analyze/landing.md).)</li><li>[!UICONTROL **Monthly**]</li><li>[!UICONTROL **Yearly**]</li></ul>|

   {style="table-layout:auto"}

### Sort the list of projects

You can sort the list of projects by any column. 

To sort the list of projects:

1. Select the column header of the column you want to sort by. 

1. (Optional) Select the same column header again to reverse the sort order.

### Search for a project

You can search the list of projects on the Component migration page to find the project that you want to migrate. 

1. In the search field at the top of the Component migration page, begin typing the name of the project that you want to migrate. 

1. Select the project when it appears in the drop-down menu. 

<!-- is there going to be a way to customize the columns that are displayed? -->
