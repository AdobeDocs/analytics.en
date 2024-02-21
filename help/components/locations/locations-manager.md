---
description: Configure the cloud import account and location where classification data can be uploaded
keywords: Analysis Workspace
title: Locations manager
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
---
# Locations manager

The Locations manager allows you to view, create, edit, or delete locations. Locations can be used for any of the following purposes: 

* Exporting files using [Data Feeds](/help/export/analytics-data-feed/create-feed.md)
* Exporting reports using [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importing schemas using [Classification sets](/help/components/classifications/sets/overview.md)

## View, filter, and search locations

The Location manager allows you to view any locations that you created. System administrators can view locations created by all users.

1. To access the Locations manager in Adobe Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Locations]**.

1. (Conditional) If you are a system administrator, you can enable the [!UICONTROL **Show all locations**] option to view locations created by all users in your organization. <!-- double-check this step and maybe add a screenshot? This is new functionality -->

1. (Optional) Select the Filter icon to filter the list of locations. 

   You can filter locations by **[!UICONTROL Location Type]**, **[!UICONTROL Account]**, or **[!UICONTROL Created By]**.

   ![Locations filters](assets/locations-filters.png)

   Or

   In the search field, begin typing the name of the location you want to view. Results are filtered as you type. The following columns are searched: **Location Name**, **Location Type**, **Account**, and **Created By**.

1. (Optional) If you have more than 1,000 locations, only the first 1,000 display. Select [!UICONTROL **Load more**] to load 1,000 more locations.

### Understand columns in the Locations manager

The following columns are available in the Locations manager. To customize the columns that are displayed iin the table, select the Customize table icon ![Customize table icon](assets/customize-table-icon.png).

* **[!UICONTROL Location name]**: The location name. Select the 3-dot menu next to a location name to either [edit the location](/help/components/locations/configure-import-locations.md) or delete it.
* **[!UICONTROL Location type]**: The type of account associated with the location.
* **[!UICONTROL Account]**: The specific account associated with the location.
* **[!UICONTROL Last used]**: The date when the location was last used.
* **[!UICONTROL Created by]**: The user who created the location.
* **[!UICONTROL Date created]**: The date that the location was created.

## Create and manage locations

You can create, edit, and delete locations.

### Create a location

For information about how to create a location, see [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### Edit a location

For information about how to edit a location, see [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).

### Delete a location

>[!IMPORTANT]
>
>If a location is deleted, any Data Feed files, Data Warehouse reports, or Classification set schemas that are associated with the deleted location will fail the next time they are used. 
>
>If you delete a location, you should [edit your Data Feeds](/help/export/analytics-data-feed/create-feed.md), [Data Warehouse reports](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), and [Classification sets schemas](/help/components/classifications/sets/manage/schema.md) to use a functioning location. 

To delete a location:

1. Select the 3-dot menu in the [!UICONTROL **Location name**] column for the the location that you want to delete.

1. Select [!UICONTROL **Delete**]. 



  
