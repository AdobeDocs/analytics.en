---
description: Steps that describe how to create a Data Warehouse request.
title: Configure a report destination for a Data Warehouse request
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
---
# Configure a report destination for a Data Warehouse request

There are various configuration options available when creating a Data Warehouse request. The following information describes how to configure a report destination for the request.

For information about how to begin creating a request, as well as links to other important configuration options, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md). 

>[!NOTE]
>
>Consider the following when configuring a report destination:
>
>* We recommend using a cloud account or email for your report destination. [Legacy FTP and SFTP accounts](#legacy-destinations) are available but are not recommended.
>
>* Any cloud accounts that you previously configured are available to use for Data Warehouse. You can configure cloud accounts in any of the following ways:
>
>   * When configuring [Data Feeds](/help/export/analytics-data-feed/create-feed.md) 
>   
>   * When [importing Adobe Analytics classification data](/help/components/locations/locations-manager.md) (Accounts can be used, but any locations that are configured on those accounts cannot be.)
>   
>   * From the Locations manager, in [Components > Locations](/help/components/locations/configure-import-accounts.md). 
>
>* Cloud accounts are associated with your Adobe Analytics user account. Other users cannot use or view cloud accounts that you configure.
>
>* You can edit any locations that you create from the Locations manager in [Components > Locations](/help/components/locations/configure-import-accounts.md)

To configure the destination where Data Warehouse reports are sent:

1. If you haven't already, begin creating a request in Adobe Analytics by selecting **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Add**].

   For additional details, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. On the New Data Warehouse request page, select the [!UICONTROL **Report destination**] tab.

   ![Report destination tab](assets/dw-report-destination.png)

1. (Conditional) If a cloud account (and a destination on that account) has already been configured in Adobe Analytics, you can use it as your report destination: 

   >[!NOTE]
   >
   >Accounts are available to you only if you configured them or if they were shared with an organization you are a part of.
   >
   >If you are a system administrator, the [!UICONTROL **Show all destinations**] option is available. Enable this option if you want to have access to all accounts and locations that were created by any user in the organization.
   
   1. Select the account from the [!UICONTROL **Select account**] drop-down menu.

      Any cloud accounts that you configured in any of the following areas of Adobe Analytics are available to use:
      
      * When importing Adobe Analytics classification data, as described in [Schema](/help/components/classifications/sets/manage/schema.md).
      
        However, any locations that are configured for importing classification data cannot be used. Instead, add a new destination as described below.

      * When configuring accounts and locations in the Locations area, as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md) and [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md).
   
   1. Select the destination associated with the account from the [!UICONTROL **Select destination**] drop-down menu. <!-- Is this correct? -->

1. (Conditional) If you don't have access to a cloud account that is already configured in Adobe Analytics, you can configure one:

   1. Select [!UICONTROL **Add account**], then specify the following information:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Account type**] | Select your cloud account type. We recommend having a single account for each account type, with multiple locations as needed within that account. <p>After choosing an account type, fields specific to that account type appear. </p>| 
      | [!UICONTROL **Account name**] | Specify a name for the account. This name appears when creating a location. <!-- true? --> | 
      | [!UICONTROL **Account description**] | Provide a short description of the account to help differentiate it from other accounts of the same account type. |

      For configuration instructions, expand the section below that corresponds to the [!UICONTROL **Account type**] that you selected.

      Use any of the following account types when configuring a report destination. For configuration instructions, expand the account type. (Additional [legacy destinations](#legacy-destinations) are also available, but are not recommended.) 

      +++Amazon S3

         To configure an Amazon S3 Role ARN account, specify the following information:

         |Field | Function | 
         |---------|----------|
         | [!UICONTROL **Role ARN**] | You must provide a Role ARN (Amazon Resource Name) that Adobe can use to gain access to the Amazon S3 account. To do this, you create an IAM permission policy for the source account, attach the policy to a user, and then create a role for the destination account. For specific information, see [this AWS documentation](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/).<p>For information about how to set up the permission of the bucket, see the article [How can I provide cross-account access to objects that are in Amazon S3 buckets?](https://repost.aws/knowledge-center/cross-account-access-s3) in the Amazon knowledge center. | 
         | [!UICONTROL **User ARN**] | The User ARN (Amazon Resource Name) is provided by Adobe. You must attach this user to the policy you created. | 

         {style="table-layout:auto"}

      +++

      +++Google Cloud Platform

         To configure a Google Cloud Platform account, specify the following information:

         |Field | Function | 
         |---------|----------|
         | [!UICONTROL **Project ID**] | Your Google Cloud project ID. See the [Google Cloud documentation about getting a project ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |  

         {style="table-layout:auto"}
   
      +++

      +++Azure SAS

         To configure an Azure SAS account, specify the following information:

         |Field | Function | 
         |---------|----------|
         | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 
         | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Key vault URI**] | <p>The path to the SAS token in Azure Key Vault.  To configure Azure SAS, you need to store an SAS token as a secret using Azure Key Vault. For information, see the [Microsoft Azure documentation about how to set and retrieve a secret from Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>After the key vault URI is created:<ul><li>Add an access policy on the Key Vault in order to grant permission to the Azure application that you created.</li><li>Make sure the Application ID has been granted the `Key Vault Certificate User` built-in role in order to access the key vault URI.</br><p>For more information, see [Azure built-in roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p></li></ul><p>For information, see the [Microsoft Azure documentation about how to assign a Key Vault access policy](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> | 
         | [!UICONTROL **Key vault secret name**] | The secret name you created when adding the secret to Azure Key Vault. In Microsoft Azure, this information is located in the Key Vault you created, on the **Key Vault** settings pages. For information, see the [Microsoft Azure documentation about how to set and retrieve a secret from Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **Secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      +++   

      +++Azure RBAC

         To configure an Azure RBAC account, specify the following information:

         |Field | Function | 
         |---------|----------|
         | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 
         | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 
         | [!UICONTROL **Secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 

         {style="table-layout:auto"}

      +++

      +++Email

         To configure an email account, specify the following information:

         |Field | Function | 
         |---------|----------|
         | [!UICONTROL **Recipients**] | Email notifications can be sent to specific users when the report is sent. Specify a single email address or a comma-separated list of email addresses. <!-- How does this differ from the Notification email tab? -->| 

   1. Select [!UICONTROL **Add location**], then specify the following information:
      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Name**] | The name of the location.  | 
      | [!UICONTROL **Description**] | Provide a short description of the account to help differentiate it from other accounts of the same account type. |
      | [!UICONTROL **Location account**] | Select the location account that you created in [Add an account](#add-an-account). | 

   1. In the [!UICONTROL **Location properties**] section, specify information specific to the account type of your location account.  

      For configuration instructions, expand the section below that corresponds to the [!UICONTROL **Account type**] that you selected previously. 

      +++Amazon S3

         To configure an Amazon S3 location, specify the following information:

         |Field | Function | 
         |---------|----------|
         | [!UICONTROL **Bucket name**] | The bucket within your Amazon S3 account where you want Adobe Analytics data to be sent. <p>Ensure that the User ARN that was provided by Adobe has the `S3:PutObject` permission in order to upload files to this bucket. This permission allows the User ARN to upload initial files and overwrite files for subsequent uploads.</p> |  
         | [!UICONTROL **Key prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, folder_name/ | 

         {style="table-layout:auto"}

      +++

      +++Google Cloud Platform

         To configure a Google Cloud Platform location, specify the following information:

         |Field | Function | 
         |---------|----------|
         | [!UICONTROL **Bucket name**] | The bucket within your GCP account where you want Adobe Analytics data to be sent. <p>Ensure that you have granted either of the following permissions to the Principal provided by Adobe:<ul><li>`roles/storage.objectCreator`: Use this permission if you  want to limit the Principal to only create files in your GCP account. </br>**Important:** If you use this permission with scheduled reporting, you must use a unique file name for each new scheduled export. Otherwise, the report generation will fail because the Principal does not have access to overwrite existing files.</li><li>`roles/storage.objectUser`: Use this permission if you want the Principal to have access to view, list, update, and delete files in your GCP account.</br>This permission allows the Principal to overwrite existing files for subsequent uploads, without the need to auto-generate unique file names for each new scheduled export.</li></ul><p>For information about granting permissions, see [Add a principal to a bucket-level policy](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) in the Google Cloud documentation.</p>|  
         | [!UICONTROL **Key prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, folder_name/ | 

         {style="table-layout:auto"}
   
      +++

      +++Azure SAS

         To configure an Azure SAS location, specify the following information:

         |Field | Function | 
         |---------|----------|
         | [!UICONTROL **Container name**] | The container within the account you specified where you want Adobe Analytics data to be sent. | 
         | [!UICONTROL **Key prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/`<p>Make sure that the SAS token store that you specified in the Key Vault secret name field when configuring the Azure SAS account has the `Write` permission. This allows the SAS token to create files in your Azure container. <p>If you want the SAS token to also overwrite files, make sure that the SAS token store has the `Delete` permission.</p><p>For more information, see [Blob storage resources](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) in the Azure Blob Storage documentation.</p>|

         {style="table-layout:auto"}

      +++   

      +++Azure RBAC

         To configure an Azure RBAC location, specify the following information:

         |Field | Function | 
         |---------|----------|
         | [!UICONTROL **Container name**] | The container within the account you specified where you want Adobe Analytics data to be sent. Ensure that you grant permissions to upload files to the Azure application that you created earlier. | 
         | [!UICONTROL **Key prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/`<p>Make sure the Application ID that you specified when configuring the Azure RBAC account has been granted the `Storage Blob Data Contributor` role in order to access the container (folder).</p> <p>For more information, see [Azure built-in roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p>|
         | [!UICONTROL **Account name**] | The   Azure storage account. | 

         {style="table-layout:auto"}

      +++
      
1. Continue configuring your Data Warehouse request on the [!UICONTROL **Report options**] tab. For more information, see [Configure report options for a Data Warehouse request](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Legacy destinations

>[!IMPORTANT]
>
>The destinations described in this section are legacy, and are not recommended. Instead, use one of the following destinations when creating a data warehouse destination: Amazon S3, Google Cloud Platform, Azure RBAC, Azure SAS, or Email. See the information above for details about each of these recommended destinations. 

The following information provides configuration information for each of the legacy destinations:

### FTP

Data warehouse data can be delivered to an Adobe or customer-hosted FTP location. Requires an FTP host, username, and password. Use the path field to place feed files in a folder. Folders must already exist; feeds throw an error if the specified path does not exist.

Use the following information when completing the available fields:

#### Account fields

* [!UICONTROL **Account name**]: The name of the FTP account.

* [!UICONTROL **Account description**]: A description of the FTP account.

* [!UICONTROL **Hostname**]: Enter the desired FTP destination URL. For example, `ftp.company.com`.
  
  >[!NOTE]
  >
  >  Do not include `ftp://` at the beginning of the URL. 

* [!UICONTROL **Username**]: Enter the username to log in to the FTP site.

* [!UICONTROL **Password and confirm password**]: Enter the password to log in to the FTP site.

#### Location fields

* [!UICONTROL **Location name**]: The name of the location on the FTP account where you want files sent.

* [!UICONTROL **Location description**]: A description of the location on the FTP account.

* [!UICONTROL **Directory path**]: The path to the location on the FTP account.

### SFTP

SFTP support for data warehouse is available. Requires an SFTP host, username, and the destination site to contain a valid RSA or DSA public key. You can download the appropriate public key when creating the data warehouse destination.

Use the following information when completing the available fields:

#### Account fields

* [!UICONTROL **Account name**]: The name of the FTP account.

* [!UICONTROL **Account description**]: A description of the FTP account.

* [!UICONTROL **Hostname**]: Enter the desired SFTP destination URL. For example, `sftp.company.com`. 

  >[!NOTE]
  >
  >  Do not include `sftp://` at the beginning of the URL. 

* [!UICONTROL **Username**]: Enter the username to log in to the SFTP site.

* [!UICONTROL **Use temporary file extensions during upload**]: When enabled, the `.part` file extension is used during the upload process. Keep this option enabled unless your SFTP server restricts file names from being changed after the upload completes.

* [!UICONTROL **Public keys**]: Download the appropriate public key when creating the data warehouse destination.

#### Location fields

* [!UICONTROL **Location name**]: The name of the location on the SFTP account where you want files sent.

* [!UICONTROL **Location description**]: A description of the location on the SFTP account.

* [!UICONTROL **Directory path**]: The path to the location on the SFTP account.

For additional information about SFTP configuration, see [Send Data Warehouse requests to SFTP servers](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md).

### S3

You can send warehouse data directly to Amazon S3 buckets. This destination type requires a Bucket name, an Access Key ID, and a Secret Key. See [Amazon S3 bucket naming requirements](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) within the Amazon S3 docs for more information.

The user you provide for uploading data warehouse data must have the following [permissions](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

The following 16 standard AWS regions are supported (using the appropriate signature algorithm where necessary):

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>The cn-north-1 region is not supported.

### Azure Blob

Data warehouse support Azure Blob destinations. Requires a container, account, and a key. Amazon automatically encrypts the data at rest. When you download the data, it gets decrypted automatically. See [Create a storage account](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) within the Microsoft Azure docs for more information.

>[!NOTE]
>
>You must implement your own process to manage disk space on the data warehouse destination. Adobe does not delete any data from the server.
