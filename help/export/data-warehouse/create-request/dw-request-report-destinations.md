---
description: Steps that describe how to create a Data Warehouse request.
title: Configure a report destination for a Data Warehouse request
feature: Data Warehouse
---
# Configure a report destination for a Data Warehouse request

There are various configuration options available when creating a Data Warehouse request. The following information describes how to configure a report destination for the request.

For information about how to begin creating a request, as well as links to other important configuration options, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md). 

1. Begin creating a request in Adobe Analytics by selecting **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Add**].

   For additional details, see [Create a Data Warehouse request](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. On the New Data Warehouse request page, select the [!UICONTROL **Report destination**] tab.

   ![Report destination tab](assets/dw-report-destination.png)

1. (Conditional) If you previously configured an account and a destination on that account that you want to use as your report destination:

   1. Select the account from the [!UICONTROL **Select account**] drop-down menu.
   
   1. Select the destination associated with the account from the [!UICONTROL **Select destination**] drop-down menu. <!-- Is this correct? -->

1. (Conditional) If you have not previously configured an account:

   1. Select [!UICONTROL **Add account**], then specify the following information:

      |Field | Function | 
      |---------|----------|
      | [!UICONTROL **Account type**] | Select your cloud account type. We recommend having a single account for each account type, with multiple locations as needed within that account. <p>After choosing an account type, fields specific to that account type appear. For configuration instructions for each account type, expand the section below that corresponds to the that you select. </p>| 
      | [!UICONTROL **Account name**] | Specify a name for the account. This name appears when creating a location. <!-- true? --> | 
      | [!UICONTROL **Account description**] | Provide a short description of the account to help differentiate it from other accounts of the same account type. |

      For configuration instructions, expand the section below that corresponds to the [!UICONTROL **Account type**] that you selected.

      Use any of the following destination types when configuring a report destination. For configuration instructions, expand the account type. (Additional legacy destinations <!-- add link --> are also available, but are not recommended.) 

      +++Amazon S3

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
         | [!UICONTROL **Secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      +++   

      +++Azure RBAC

         Specify the following information to configure an Azure RBAC account:

         |Field | Function | 
         |---------|----------|
         | [!UICONTROL **Application ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 
         | [!UICONTROL **Tenant ID**] | Copy this ID from the Azure application that you created. In Microsoft Azure, this information is located on the **Overview** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 
         | [!UICONTROL **Secret**] | Copy the secret from the Azure application that you created. In Microsoft Azure, this information is located on the **Certificates & secrets** tab within your application. For more information, see the [Microsoft Azure documentation about how to register an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). | 

         {style="table-layout:auto"}

      +++

      +++Email

         Specify the following information to configure an email account:

         |Field | Function | 
         |---------|----------|
         | [!UICONTROL **Recipients**] | Email notifications can be sent to specific users when the report is sent. Specify a single email address or a comma-separated list of email addresses. <!-- How does this differ from the Notification email tab? -->| 

   1. Select [!UICONTROL **Add destination**], then ... <!--need to go through this -->

1. Continue configuring your Data Warehouse request on the [!UICONTROL **Report options**] tab. For more information, see [Configure report options for a Data Warehouse request](/help/export/data-warehouse/create-request/dw-request-report-options.md).