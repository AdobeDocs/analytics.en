---
description: Configure the cloud import account and location where classification data can be uploaded
keywords: Analysis Workspace
title: Locations manager
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
---
# Locations manager

The Locations manager allows you to view, create, edit, or delete accounts and locations. These can be used for any of the following purposes: 

* Exporting files using [Data Feeds](/help/export/analytics-data-feed/create-feed.md)
* Exporting reports using [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importing schemas using [Classification sets](/help/components/classifications/sets/overview.md)

## View, filter, and search locations

The Location manager allows you to view any locations that you created. System administrators can view locations created by all users.

1. To access the Locations manager in Adobe Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Locations]**.

1. (Conditional) If you are a system administrator, you can enable the [!UICONTROL **View locations for all users**] option to view locations created by all users in your organization. <!-- Maybe add a screenshot? This is new functionality -->

1. Filter or search the list of locations:

   * **Filter:** Select the Filter icon to filter the list of locations. 

     You can filter locations by **[!UICONTROL Location Type]**, **[!UICONTROL Account]**, or **[!UICONTROL Created By]**.

     ![Locations filters](assets/locations-filters.png)

   * **Search:** In the search field, begin typing the name of the location you want to view. Results are filtered as you type. The following columns are searched: **Location Name**, **Location Type**, **Account**, and **Created By**.

1. (Optional) If you have more than 1,000 locations, only the first 1,000 display. Select [!UICONTROL **Load more**] to load 1,000 more locations.

## Configure columns in the Locations manager

The following columns are available in the Locations manager. To customize the columns that are displayed in the table, select the **Customize table** icon ![Customize table icon](assets/customize-table-icon.png).

* **[!UICONTROL Location name]**: The location name. Select the 3-dot menu next to a location name to either [edit the location](/help/components/locations/configure-import-locations.md) or delete it.
* **[!UICONTROL Location type]**: The type of account associated with the location.
* **[!UICONTROL Account]**: The specific account associated with the location.
* **Application**: The type of application that the location can be used with (such as Data Feeds, Data Warehouse, or Classification sets).
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

To delete a location in the Locations manager in Adobe Analytics:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Locations]**, then select the [!UICONTROL **Locations**] tab.

1. Select the 3-dot menu in the [!UICONTROL **Location name**] column for the location that you want to delete.

1. Select [!UICONTROL **Delete**]. 

## Create and manage accounts

You can create, edit, and delete accounts.

### Create an account

For information about how to create an account, see [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md).

### Edit an account

For information about how to edit an account, see [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md).

### View account keys

After you create an account, you can view any associated account keys for that account. You might need to view this information if you didn't finish configuring the account with your cloud provider when you [originally configured the account](/help/components/locations/configure-import-accounts.md).

To view keys associated with an export account:

1. In Adobe Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Locations]**, then select the [!UICONTROL **Location accounts**] tab.

1. (Conditional) If you are a system administrator, you can enable the [!UICONTROL **View locations for all users**] option to view locations created by all users in your organization. <!-- Maybe add a screenshot? This is new functionality -->

1. Select the 3-dot icon on the account that you want to edit, then select [!UICONTROL **Account keys**].

### Delete an account

>[!IMPORTANT]
>
>Accounts can be deleted only if there are no locations using it. Before you delete an account, you must first delete any locations on the account, as described in [Delete a location](#delete-a-location).

1. In Adobe Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Locations]**, then select the [!UICONTROL **Location accounts**] tab.

1. (Conditional) If you are a system administrator, you can enable the [!UICONTROL **View accounts for all users**] option to view locations created by all users in your organization. 

1. Select the 3-dot icon on the account that you want to edit, then select [!UICONTROL **Delete account**]

## Configure company-wide settings (administrators only)

System administrators can restrict users from creating accounts and locations, or they can limit the types of accounts users can create and use. 

### Configure whether users can create and edit accounts

By default, all users in the organization can create accounts and edit accounts they create in your Adobe Analytics environment, as described in [configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md).

You can restrict users from creating accounts. When you do, users can still use any accounts they have already created, but they can no longer edit them. You can delete accounts that users have created, as described in [Delete an account](#delete-an-account).

To restrict all users from creating and editing accounts:

1. In Adobe Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Locations]**, then select the [!UICONTROL **Admin settings**] tab.

1. In the [!UICONTROL **Locations accounts**] section, deselect the option, [!UICONTROL **Allow users to create and manage location accounts**].

1. Select [!UICONTROL **Save**].

1. (Optional) Delete any accounts that users have created that you no longer want them to use, as described in [Delete an account](#delete-an-account).

### Configure whether users can create and edit locations

By default, all users in the organization can create locations and edit locations they create in your Adobe Analytics environment, as described in [configure cloud import and export locations](/help/components/locations/configure-import-locations.md).

You can restrict users from creating locations. When you do, users can still use any locations they have already created, but they can no longer edit them. You can delete locations that users have created, as described in [Delete locations](#delete-a-location).

To restrict all users from creating and editing locations:

1. In Adobe Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Locations]**, then select the [!UICONTROL **Admin settings**] tab.

1. In the [!UICONTROL **Locations**] section, deselect the option, [!UICONTROL **Allow users to create and manage locations**].

1. Select [!UICONTROL **Save**].

1. (Optional) Delete any locations that users have created that you no longer want them to use, as described in [Delete a location](#delete-a-location).

### Limit which accounts types users can create and use

You can limit the account types users see in the following circumstances:

* When [creating new accounts](/help/components/locations/configure-import-accounts.md).

* When choosing which accounts to use when exporting files using [Data Feeds](/help/export/analytics-data-feed/create-feed.md), exporting reports using [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), or importing schemas using [Classification sets](/help/components/classifications/sets/overview.md).  

When you limit account types as described in this section, any accounts of the type that you limit are no longer visible to users. This means that new accounts of that type cannot be created, and existing accounts of that type cannot be used when creating Data Feeds, Data Warehouse, or Classification sets. 

However, existing accounts that are configured for scheduled exports must be deleted if you want to restrict them from being used.

#### Ensure that accounts are not used for scheduled exports

When you limit account types, existing accounts are hidden, not deleted. 

If schedules are already configured to send data to an account that is of the type that you limit, the schedules will continue to run even after you limit the account type, and data will continue to be sent to the account.  For example, if a Data Feed is scheduled to send data to an account type that you limit, the schedule will continue to run.

If you need to ensure that accounts of a certain type are not used in scheduled exports, you can delete the accounts before you [limit the account types](#limit-the-account-types-that-are-available-to-users).

To delete accounts:

1. Locate the accounts of the account type you plan to limit, which are being used for scheduled exports. 

1. Delete the accounts, as described in [Delete an account](#delete-an-account).

1. Continue with the following section, [Limit the account types that are available to users](#limit-the-account-types-that-are-available-to-users).

#### Limit the account types that are available to users

To limit the account types that are available to users when creating and using accounts:

1. In Adobe Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Locations]**, then select the [!UICONTROL **Admin settings**] tab.

1. Locate the [!UICONTROL **Permitted account types**] section.

   The following account types are available to users by default. 
  
   Deselect any of these account types that you want to restrict users from using. 
  
   * [!UICONTROL **Amazon S3 Role ARN**]

   * [!UICONTROL **Google Cloud Platform**]

   * [!UICONTROL **Azure SAS**]

   * [!UICONTROL **Azure RBAC**]

   * [!UICONTROL **Email**]

   * Legacy account types, including [!UICONTROL **Amazon S3**], [!UICONTROL **Azure**], [!UICONTROL **FTP**], and [!UICONTROL **SFTP**]

1. Select [!UICONTROL **Save**].


