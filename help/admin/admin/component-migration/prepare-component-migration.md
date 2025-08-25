---
description: Explains the necessary preparations to prepare to migrate components and projects from Adobe Analytics to Customer Journey Analytics.
title: Prepare to migrate components and projects from Adobe Analytics to Customer Journey Analytics
feature: Admin Tools
exl-id: a9ff98dc-6568-428d-a8a8-faca5bc76a29
---
# Prepare to migrate components and projects from Adobe Analytics to Customer Journey Analytics

Before anyone in your organization begins migrating projects as described in [Migrate components and projects from Adobe Analytics to Customer Journey Analytics](/help/admin/admin/component-migration/component-migration.md), complete the following sections.

## Prerequisites

Before your projects and their associated components are ready to migrate, you first need to follow the steps in [Evolution from Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html) in the Adobe Customer Journey Analytics Guide. These steps include:

1. Use either of the following methods to ingest data into Adobe Experience Platform in order to view Adobe Analytics report suite data in Customer Journey Analytics:

   >[!NOTE]
   >
   >  When you use the WebSDK to ingest data, all schema fields must be manually mapped. (For more information about the mapping process, see [Migrate components and projects from Adobe Analytics to Customer Journey Analytics](/help/admin/admin/component-migration/component-migration.md))


   * To use the Adobe Analytics source connector, you need to:

      1. [Set up report suites for ingestion into Adobe Experience Platform and Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [Ingest and use the data](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html)

   * To use the WebSDK, you need to:
  
     1. [Set up report suites for ingestion into Adobe Experience Platform and Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)
    
     1. [Ingest data via the Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk.html)

1. Create a [connection](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html) and [data view](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html) with the data ingested. 

1. Ensure that users in Customer Journey Analytics are provisioned to the data views where data is being mapped. 

   For more information, see [Customer Journey Analytics permissions in the Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html#customer-journey-analytics-permissions-in-admin-console) in [Customer Journey Analytics access control](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

   The Permissions tab is part of each product profile in Admin Console. You can add users to specific product profiles. Then you assign rights to specific data views and specify which permissions the users in a product profile have. 

1. Decide as an organization how you will map components. 

   For more information, see the section below, [Decide as an organization how you will map components](#decide-as-an-organization-how-you-will-map-components).

## Understand what is included in a migration

The following tables outline which elements of a project and component are included in a migration:

### Component elements that are migrated

Dimensions and metrics are migrated as part of the mapping process described in [Migrate Adobe Analytics projects to Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics). 

Segments, date ranges, and calculated metrics that don't already exist in Customer Journey Analytics are re-created there based on the dimensions and metrics that are mapped. 

|  | Migrated |
|---------|---------|
| **[Owner](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)** | Dimensions and metrics: No<p>Segments and date ranges: ![check mark](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Sharing](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensions and metrics: No<p>Segments and date ranges: No</p> |
| **[Descriptions](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimensions and metrics: No<p>Segments and date ranges: ![check mark](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Tags](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensions and metrics: No<p>Segments and date ranges: No</p> |
| **[Attribution (on dimensions)](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimensions and metrics: No<p>Segments and date ranges: No</p> |

{style="table-layout:auto"}

### Project elements that are migrated

|  | Migrated | 
|---------|----------|
| **[Date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![check mark](assets/Smock_Checkmark_18_N.svg) | 
| **[Segments](/help/components/segmentation/seg-overview.md)** | ![check mark](assets/Smock_Checkmark_18_N.svg) | 
| **[Quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![check mark](assets/Smock_Checkmark_18_N.svg) | 
| **[Dimensions](/help/components/dimensions/overview.md)** | ![check mark](assets/Smock_Checkmark_18_N.svg) Mapped automatically or manually | 
| **[Metrics](/help/components/metrics/overview.md)** | ![check mark](assets/Smock_Checkmark_18_N.svg) Mapped automatically or manually | 
| **[Panels](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![check mark](assets/Smock_Checkmark_18_N.svg) | 
| **[Visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![check mark](assets/Smock_Checkmark_18_N.svg) |
| **[Owner](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![check mark](assets/Smock_Checkmark_18_N.svg) Defined by user doing the migration | 
| **[Curation](/help/analyze/analysis-workspace/curate-share/curate.md)** | No | 
| **[Sharing](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | No | 
| **[Annotations](/help/analyze/analysis-workspace/components/annotations/overview.md)** | No | 
| **[Folder structure](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | No | 
| **[Descriptions](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![check mark](assets/Smock_Checkmark_18_N.svg) | 
| **[Tags](/help/analyze/landing.md)** | No | 
| **[Favorites](/help/analyze/landing.md)** | No | 
| **[Schedules](/help/components/scheduled-projects-manager.md)** | No |
| **[Anomaly Detection](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)** | ![check mark](assets/Smock_Checkmark_18_N.svg) |

{style="table-layout:auto"}

## Understand unsupported elements that cause errors

The following visualizations and panels are not supported in Customer Journey Analytics. When these elements are included in a project prior to migration, they can either cause the migration to fail or they can result in errors after the project is migrated.

Remove these elements from the Adobe Analytics project before migrating the project to Customer Journey Analytics. If a migration fails, remove these elements before retrying the migration.

### Unsupported Panels

* [Analytics for Target (A4T)](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [Segment comparison](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [Media Average Minute Audience](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [Next or previous item](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [Page summary](/help/analyze/analysis-workspace/c-panels/page-summary.md)

* [Contribution Analysis](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)

## Decide as an organization how you will map components

>[!NOTE]
>
>The migration process identifies components in your Adobe Analytics project that can't be automatically mapped to components in Customer Journey Analytics, and it allows you to manually map them. 
>
>**Any mappings made on one project apply to all future projects across your entire IMS org, regardless of which user is performing the migration. These mappings can be updated when migrating future projects.** 
>
>It's important that your organization decides how dimensions and metrics will be mapped before any projects are migrated. Doing so avoids individual administrators making decisions in a silo when considering only a single project.
>
>Following is a list of dimensions and metrics that you must manually map if they exist in your project. We recommend reviewing this list before your migration. If any of these components exist in your project, decide now which Customer Journey Analytics components you will map them to.


### Dimensions that must be manually mapped

* averagepagetime
* pagetimeseconds
* singlepagevisits
* visitnumber
* timeprior
* timespent
* category
* connectiontype
* customerloyalty
* customlink
* downloadlink
* exitlink
* hitdepth
* hittype
* pathlength
* daysbeforefirstpurchase
* dayssincelastpurchase
* dayssincelastvisit
* identificationstate
* optoutreason
* persistentcookie
* returnfrequency
* searchenginenatural
* searchenginenaturalkeyword
* mobilecarrier
* monitorresolution
* surveybase
* mcaudiences
* tntbase
* targetraw


### Metrics that must be manually mapped

* timespentvisit
* timespentvisitor
* reloads
* bounces
* bouncerate
* pageevents
* pageviewspervisit
* orderspervisit
* averagepagedepth
* averagetimespentonsite
* exitlinkinstances
* customlinkinstances
* downloadlinkinstances
* darkvisitors
* singlepagevisits
* singlevaluevisits
* visitorhomepage
* visitorsmcvisid
* pagesnotfound
* newengagements
* time_granularity
* concurrent_viewers_visitors
* concurrent_viewers_occurrences
* devices
* estimatedpeople
* playback_time_spent_seconds
* playback_time_spent_minutes
* average_minute_audience_time_based
* average_minute_audience_media_time
* average_minute_audience_content_time
* video_length
* targetconversion
* targetimpression
