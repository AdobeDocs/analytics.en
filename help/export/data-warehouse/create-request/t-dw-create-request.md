---
description: Steps that describe how to create a Data Warehouse request.
title: Create a Data Warehouse request
feature: Data Warehouse
exl-id: c38de0da-feea-4f01-8e2f-8409367afb45
---
# Create a Data Warehouse request

There are various configuration options available when creating a Data Warehouse request. The following information describes how to begin creating a request, then provides links to more detailed information. 

## Begin creating a Data Warehouse request

1. In Adobe Analytics, select **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]**.

1. On the [!UICONTROL **Data Warehouse**] page, select [!UICONTROL **Add**].

   ![Button to add a request](assets/dw-add-request.png)

   The New Data Warehouse request page is displayed.

   ![General settings tab](assets/dw-general-settings.png)

## Complete the Data Warehouse request

Various tabs are available when creating a Data Warehouse request. For information about the various configuration options on each tab, see the following articles:



1. On the [!UICONTROL **General settings**] tab, complete the following fields:

   |Option | Function | 
   |---------|----------|
   | Request name | Identifies the request. | 
   | Date ranges | Select the date range to be included in the report. <p>You can choose custom dates, or a preset date range. Preset ranges are relative to the date the report is sent.</p><p>The following preset options are available:</p><ul><li>Today</li><li>Yesterday</li><li>Last 7 days</li><li>Last 30 days</li><li>This week</li><li>Last week</li><li>Last 2 weeks</li><li>Last 3 weeks</li><li>Last 4 weeks</li><li>This month</li><li>Last month</li><li>Last hour</li><li>Today</li><li>Today</li></ul> | 
   | Granularity | <!--what does this setting do? It's not the schedule/frequency... -->The frequency in which the report is sent.<p>The following options are available:</p><ul><li>None<p>Choose this option if you want to </p></li><li>Yesterday</li><li>Last 7 days</li><li>Last 30 days</li><li>This week</li><li>Last week</li><li>Last 2 weeks</li><li>Last 3 weeks</li><li>Last 4 weeks</li><li>This month</li><li>Last month</li><li>Last hour</li><li>Today</li><li>Today</li></ul> | 

1. Complete the following additional 

1. Select the [!UICONTROL **Build your report**] tab, then

1. Select the [!UICONTROL **Report destination**] tab,

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

   +++Snowflake

      Specify the following information to configure a Snowflake account:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Account**] | <!--add info --> | 
      | [!UICONTROL **User**] | <!--add info --> | 
      | [!UICONTROL **Location Account Secret**] | Copy the secret from the Snowflake application that you created. In Snowflake, this information is located in <!--add link to Snowflake docs -->. | 

   +++

   +++Adobe Experience Platform

      Specify the following information to configure an Adobe Experience Platform account:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Location Account Secret**] | Copy the secret from the Adobe Experience Platform application that you created. In Adobe Exprience Platform, this information is located in <!--add link to AEP docs -->. | 

   +++

1. Select [!UICONTROL **Save**].

1. Select the [!UICONTROL **Report options**] tab,

1. Select the [!UICONTROL **Scheduling options**] tab,

1. Select the [!UICONTROL **Notification email**] tab,



configure the options described in [Data Warehouse Requests Descriptions](/help/export/data-warehouse/data-warehouse.md#section_F21C78ED36884C389C852E876AF5CDE8)
1. Click **[!UICONTROL Request this Report]**.
