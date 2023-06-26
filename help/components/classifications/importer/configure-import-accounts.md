---
description: Configure the cloud import account and location where classification data can be uploaded
keywords: Analysis Workspace
title: Configure cloud import locations
feature: Classifications
---
# Configure cloud import locations

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Before you can import Adobe Analytics data from a cloud destination, you need to add and configure the location where you want the data to be sent. 

This process consists of adding and configuring the account (such as Amazon S3 Role ARN, Google Cloud Platform, and so forth) and the location within the account (such as a folder within the account).

## Add an account

You need to configure Adobe Analytics with the necessary information to access your cloud destination account.

1. In Adobe Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Locations**].
1. On the [!UICONTROL Locations] page, select the [!UICONTROL **Location accounts**] tab.
1. Select [!UICONTROL **Add account**]. <!-- add screenshot? -->
   
   The Add account dialog displays.
1. Specify the following information:
   |Field | Function | 
   |---------|----------|
   | [!UICONTROL **Location account name**] | The name of the location account. This name appears when creating a location | 
   | [!UICONTROL **Location account description**] | Provide a short description of the account to help differentiate it from other accounts of the same account type. |
   | [!UICONTROL **Account type**] | B3 | 
1. In the [!UICONTROL **Account properties**] section, specify information specific to the account type that you selected.  

   For configuration instructions, expand the section below that corresponds to the [!UICONTROL **Account type**] that you selected. 

   +++Amazon S3 Role ARN

      Specify the following information to configure an Amazon S3 Role ARN account:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Role ARN**] | You must provide a Role ARN (Amazon Resource Name) that Adobe can use to gain access to the Amazon S3 account. To do this, you create an IAM permission policy for the source account, attach the policy to a user, and then create a role for the destination account. For specific information, see [this AWS documentation](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). | 
      | [!UICONTROL **User ARN**] | The User ARN (Amazon Resource Name) is provided by Adobe. You must attach this user to the policy you created. | 

      {style="table-layout:auto"}

   +++

   +++Google Cloud Platform

      Specify the following information to configure a Google Cloud Platform account:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Project ID**] | Your Google Cloud project ID. See the [Google Cloud documentation about getting a project ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |  

      {style="table-layout:auto"}
   
   +++

   +++Azure SAS

      Specify the following information to configure an Azure SAS account:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 
      | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Key vault URI**] | <p>The path to the SAS token in Azure Key Vault.  To configure Azure SAS, you need to store an SAS token as a secret using Azure Key Vault. For information, see the [Microsoft Azure documentation about how to set and retrieve a secret from Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>After the key vault URI is created, add an access policy on the Key Vault in order to grant permission to the Azure application that you created. For information, see the [Microsoft Azure documentation about how to assign a Key Vault access policy](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> | 
      | [!UICONTROL **Key vault secret name**] | The secret name you created when adding the secret to Azure Key Vault. In Microsoft Azure, this information is located in the Key Vault you created, on the **Key Vault** settings pages. For information, see the [Microsoft Azure documentation about how to set and retrieve a secret from Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Location Account Secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

   +++   

   +++Azure RBAC

      Specify the following information to configure an Azure RBAC account:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 
      | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 
      | [!UICONTROL **Location Account Secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 

      {style="table-layout:auto"}

   +++

1. Select [!UICONTROL **Save**].

1. Continue with [Add a location](#add-a-location).

## Add a location

1. You need to add an account before you can add a location. [Add an account](#add-an-account) if you haven't already.
1. In Adobe Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Locations**].
1. On the [!UICONTROL Locations] page, select the [!UICONTROL **Locations**] tab.
1. Select [!UICONTROL **Add location**]. <!-- add screenshot? -->
   
   The Location dialog displays.
1. Specify the following information:
   |Field | Function | 
   |---------|----------|
   | [!UICONTROL **Location name**] | The name of the location.  | 
   | [!UICONTROL **Location description**] | Provide a short description of the account to help differentiate it from other accounts of the same account type. |
   | [!UICONTROL **Location accounts**] | Select the location account that you created in [Add an account](#add-an-account). | 

1. In the [!UICONTROL **Location properties**] section, specify information specific to the account type of your location account.  

   For configuration instructions, expand the section below that corresponds to the account type that you selected in the [!UICONTROL **Location accounts**] field. 

   +++Amazon S3 Role ARN

      Specify the following information to configure an Amazon S3 Role ARN location:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Bucket**] | The bucket within your Amazon S3 account where you want Adobe Analytics data to be sent. Ensure that the User ARN that was provided by Adobe has access to upload files to this bucket. |  
      | [!UICONTROL **Prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, folder_name/ | 

      {style="table-layout:auto"}

   +++

   +++Google Cloud Platform

      Specify the following information to configure a Google Cloud Platform location:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Bucket**] | The bucket within your GCP account where you want Adobe Analytics data to be sent. Ensure that you have granted permission to the Principal provided by Adobe to upload files to this bucket. |  
      | [!UICONTROL **Prefix**] | The folder within the bucket where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, folder_name/ | 

      {style="table-layout:auto"}
   
   +++

   +++Azure SAS

      Specify the following information to configure an Azure SAS location:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Container**] | The container within the account you specified where you want Adobe Analytics data to be sent. | 
      | [!UICONTROL **Prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/` |

      {style="table-layout:auto"}

   +++   

   +++Azure RBAC

      Specify the following information to configure an Azure RBAC location:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Container**] | The container within the account you specified where you want Adobe Analytics data to be sent. Ensure that you grant permissions to upload files to the Azure application that you created earlier. | 
      | [!UICONTROL **Prefix**] | The folder within the container where you want to put the data. Specify a folder name, then add a backslash after the name to create the folder. For example, `folder_name/` |
      | [!UICONTROL **Account**] | The Azure storage account. | 

      {style="table-layout:auto"}

   +++

1. Select [!UICONTROL **Save**].

   You can now import data to the account and location that you configured.