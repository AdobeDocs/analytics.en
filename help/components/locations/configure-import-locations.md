---
description: Configure the cloud import account and location where classification data can be uploaded
keywords: Analysis Workspace
title: Configure cloud import locations
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
---
# Configure cloud import and export locations

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

You can configure a cloud account (and a location on that account) that is used for the following purposes:

* Importing data to [Classification sets](/help/components/classifications/sets/manage/schema.md) 

* Exporting data with [Data Feeds](/help/export/analytics-data-feed/create-feed.md) and [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)

You need to configure Adobe Analytics with the necessary information to access your cloud account. This process consists of adding and configuring the account (such as Amazon S3 Role ARN, Google Cloud Platform, and so forth) as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md), and then adding and configuring the location within that account (as described in this article).

To configure a cloud import or export location:

1. You need to add an account before you can add a location. If you haven't already, add an account as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md).
1. In Adobe Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Locations**].
1. On the [!UICONTROL Locations] page, select the [!UICONTROL **Locations**] tab.
1. Select [!UICONTROL **Add location**]. <!-- add screenshot? -->
   
   The Location dialog displays.
1. Specify the following information:
   |Field | Function | 
   |---------|----------|
   | [!UICONTROL **Name**] | The name of the location.  | 
   | [!UICONTROL **Description**] | Provide a short description of the account to help differentiate it from other accounts of the same account type. |
   | [!UICONTROL **Location account**] | Select the location account that you created in [Add an account](#add-an-account). | 

1. In the [!UICONTROL **Location properties**] section, specify information specific to the account type of your location account.  

   For configuration instructions, expand the section below that corresponds to the account type that you selected in the [!UICONTROL **Location accounts**] field. 

   +++Amazon S3 Role ARN

      Specify the following information to configure an Amazon S3 Role ARN location:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Bucket name**] | The bucket within your Amazon S3 account where you want Adobe Analytics data to be sent. |  
      | [!UICONTROL **Key prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, folder_name/ | 

      {style="table-layout:auto"}

   +++

   +++Google Cloud Platform

      Specify the following information to configure a Google Cloud Platform location:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Bucket name**] | The bucket within your GCP account where you want Adobe Analytics data to be sent. Ensure that you have granted permission to the Principal provided by Adobe to upload files to this bucket. |  
      | [!UICONTROL **Key prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, folder_name/ | 

      {style="table-layout:auto"}
   
   +++

   +++Azure SAS

      Specify the following information to configure an Azure SAS location:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Container name**] | The container within the account you specified where you want Adobe Analytics data to be sent. | 
      | [!UICONTROL **Key prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/` |

      {style="table-layout:auto"}

   +++   

   +++Azure RBAC

      Specify the following information to configure an Azure RBAC location:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Container name**] | The container within the account you specified where you want Adobe Analytics data to be sent. Ensure that you grant permissions to upload files to the Azure application that you created earlier. | 
      | [!UICONTROL **Key prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/` |
      | [!UICONTROL **Account name**] | The Azure storage account. | 

      {style="table-layout:auto"}

   +++

1. Select [!UICONTROL **Save**].

   You can now import data from the account and location that you configured.

   Data is not deleted from the cloud destination after it is imported. 

   >[!NOTE]
   >
   >   If you previously used [FTP to import classifications](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) to Adobe Analytics, you needed to upload a FIN file. This FIN file is not needed when importing from cloud accounts.

