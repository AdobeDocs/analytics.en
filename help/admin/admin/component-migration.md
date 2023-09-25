---
description: Explains how to migrate components and projects from Adobe Analytics to Customer Journey Analytics.
title: Migrate components and projects from Adobe Analytics to Customer Journey Analytics
feature: Admin Tools
---
# Migrate components and projects from Adobe Analytics to Customer Journey Analytics

Adobe Analytics administrators can migrate Adobe Analytics components and projects to Customer Journey Analytics. 

The migration process includes:

* Projects from Adobe Analytics are automatically re-created in Customer Journey Analytics

* Dimensions and metrics from Adobe Analytics report suites are mapped to dimensions and metrics in Customer Journey Analytics data views. 

## Prerequisites

Before your components and project are ready to migrate, you first need to use the Analytics source connector to view Adobe Analytics report suite data in Customer Journey Analytics. To do that, you need to:

* [Set up report suites for ingestion into Adobe Experience Platform and Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

* [Ingest and use the data](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html)

* Users in Customer Journey Analytics are provisioned to the data views where data is being mapped. 

  For more information, see [Customer Journey Analytics permissions in the Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Customer Journey Analytics access control](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).


The Permissions tab is part of each product profile in Admin Console. You can add users to specific product profiles. Then you assign rights to specific data views and specify which permissions the users in a product profile have. 

## Migrate Adobe Analytics projects to Customer Journey Analytics

1. In Adobe Analytics select the [!UICONTROL **Admin**] tab, then select [!UICONTROL **All admin**].

1. Under [!UICONTROL **Data configuration & collection**], select [!UICONTROL **Component migration**].

  <!-- add screenshot -->

1. (Conditional) To quickly find the project that you want to migrate, you can either:

   * Filter the list of projects by selecting the Filter icon. 

     You can filter by the following criteria:

     * Status

     * Tags

     * Report suite

     * Owners

     * Other filters

   * Use the search field to search for the project you want to migrate. 

1. Select the project that you want to migrate, then select [!UICONTROL **Migrate to Customer Journey Analytics**].

   Or

   Mouse over the project that you want to migrate, then select the **Migrate** icon.

   You can select only one project at a time to migrate.
   
1. 