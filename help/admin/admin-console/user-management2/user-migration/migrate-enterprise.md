---
description: How to migrate Analytics user accounts as Enterprise or Federated IDs to the Admin Console.
title: Migrate Analytics user accounts for Enterprise and Federated IDs
feature: Admin Tools
exl-id: 988ed685-4eca-4b0b-a653-9c6a156852f1
---
# Migrate Analytics user accounts for Enterprise and Federated IDs{#migrate-analytics-user-accounts-for-enterprise-and-federated-ids}

How to migrate Analytics user accounts as Enterprise or Federated IDs to the Admin Console.

## Prerequisites {#prereqs}

Prerequisites to managing users in the Admin Console.

For new domains and directories, follow the steps to:

* Set up a directory
* Set up domains
* Link domains to directories

See [Set up an identity system](https://helpx.adobe.com/enterprise/using/set-up-identity.html) for help.

If a directory was already created in another organization by another business unit or team, follow the steps in [directory trusting](https://helpx.adobe.com/enterprise/using/set-up-identity.html#Directorytrusting) to establish the directory in the organization that you are using for Analytics.

## Migrate user accounts for Enterprise and Federated IDs {#task-0cfb3e4400fd4ab58e4d9704528b05fa}

In this procedure, you will:

* Download a user login list from **[!UICONTROL Analytics]** > **[!UICONTROL Analytics Users & Assets]**.

* Download a current users list from the **[!UICONTROL Admin Console]** > **[!UICONTROL Users]**.

* Compare the lists (looking for duplicates so that you avoid overwriting account data in the Admin Console).
* Upload a finished [!DNL .csv] (from **[!UICONTROL Admin Console]** > **[!UICONTROL Users]**) with Enterprise ID or Federated ID users to the Admin Console.

If you need to migrate existing Adobe ID user accounts to an Enterprise ID or Federated ID, contact Adobe Customer Care and request a [bulk user identity switch](https://helpx.adobe.com/enterprise/using/bulk-operations.html).

**To migrate user accounts** 

1. Download the Analytics user logins file ( [!DNL User Logins List.tab]) from Analytics User Management, using one of the following methods (depending on whether you already migrated users).
   1. *Prior to migration,* navigate to **[!UICONTROL Admin]** > **[!UICONTROL User Management (Legacy)]** > **[!UICONTROL Edit Users]**, then click **[!UICONTROL Download Report]**.
   
      ![](/help/admin/admin-console/user-management2/user-migration/assets/download-report.png)

      The Download Report link displays only for customers who have not migrated users.
   
   1. *If you already migrated users,* navigate to **[!UICONTROL Analytics]** > **[!UICONTROL Analytics users and Assets]**.
   
      ![Step Info](/help/admin/admin-console/user-management2/user-migration/assets/admin-analytics-users-assets.png)

   1. On the [!DNL Users] page, select users, then click **[!UICONTROL Export to CSV]**.
   
      ![Step Info](/help/admin/admin-console/user-management2/user-migration/assets/export-csv-migrate.png)

   1. Open the downloaded [!DNL User List.csv] file in Excel.
   
      Be prepared to copy the *`Email`*, *`First Name`*, and *`Last Name`* values to a [!DNL sample.csv] file (described in the next step).

      >[!IMPORTANT]
      >
      >The values in the CSV file must be comma delimited.

      >[!TIP]
      >
      >During this step, Adobe recommends streamlining your user list to ensure that only those users with a valid email ID are included in the Enterprise or Federated ID migration.
   
1. In the [!UICONTROL Admin Console], download a list of Admin Console users:

   1. Navigate to [!UICONTROL Admin Console] > **[!UICONTROL Users]**, then click [Export users list to CSV](https://helpx.adobe.com/enterprise/using/users.html).
   
      ![](/help/admin/admin-console/user-management2/user-migration/assets/export-csv.png)

   1. Compare the two files: the existing Admin Console users in the exported [!DNL .csv] file ( [!DNL sample.csv], in this example) with the users in the Analytics [!DNL User Logins List.csv] file.

      >[!IMPORTANT]
      >
      >If you find duplicates, delete them from the Analytics [!DNL User Logins List.csv] file. This step helps prevent overwriting existing Experience Cloud user permissions in the Admin Console and gives you a list of accounts to migrate.

1. Download the CSV template from the Admin Console:
   1. On the Users tab, click **[!UICONTROL Add users by CSV]**, then **[!UICONTROL Download CSV Template]**.
   
      ![Step Info](/help/admin/admin-console/user-management2/user-migration/assets/add-users-csv.png)

   1. Choose **[!UICONTROL Standard Template]**.
   
      This step downloads a [!DNL sample.csv] template file.

      ![](/help/admin/admin-console/user-management2/user-migration/assets/download-csv-template.png)

1. Copy the *`Email`*, *`First Name`*, and *`Last Name`* column values from [!DNL User Logins List.tab] to the corresponding columns in the [!DNL sample.csv] template.

   **Template File Example**

   ![](/help/admin/admin-console/user-management2/user-migration/assets/sample.png)

1. In the template ( [!DNL sample.csv]), complete the following required fields:

<table id="table_1B5EEFDB5BD8436EB760BE5FFAB1CF02"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Email </p> </td> 
   <td colname="col2"> <p>Copied from the <span class="filepath"> User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>First Name </p> </td> 
   <td colname="col2"> <p>Copied from the <span class="filepath"> User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Last Name </p> </td> 
   <td colname="col2"> <p>Copied from the <span class="filepath"> User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identity Type </p> </td> 
   <td colname="col2"> <p><span class="term"> Federated ID</span> or <span class="term"> Enterprise ID</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domain </p> </td> 
   <td colname="col2"> <p>Ensure that domains in <span class="term"> Domain</span> and <span class="term"> Email</span> column are matching the domain(s) established in the prerequisites</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Country Code </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

   For more information about the fields in the [!DNL .csv] file, see [CSV file format](https://helpx.adobe.com/enterprise/using/users.html).

   >[!NOTE]
   >
   >Other columns, such as [!UICONTROL Product Configurations] and [!UICONTROL Admin Roles] can be blank.

1. On the Users tab in the Admin Console, upload the template file by clicking **[!UICONTROL Add users by CSV]** (as shown in Step 3.).
1. In Analytics, run the migration tool (as described in [Migrate Analytics user accounts](/help/admin/admin-console/user-management2/user-migration/t-migrate-users.md)).
1. Click **[!UICONTROL Migrate]** > **[!UICONTROL Migrate as Enterprise IDs]**.

   ![Step Info](/help/admin/admin-console/user-management2/user-migration/assets/migrate-as-enterprise.png)

   When you click **[!UICONTROL Migrate]**, user are linked to the Enterprise ID/Federated ID account in Admin Console. The permissions of the legacy user account in Analytics will match the permissions granted to the Enterprise/Federated ID login in **[!UICONTROL Admin Console]** > **[!UICONTROL Analytics]** > **[!UICONTROL Product Profiles]**. The user ID displays in the Migration Completed bucket. You can disable their legacy [!DNL my.omniture.com] access.

   After migrating users, the status under the Migration Status column changes from **[!UICONTROL Not Initiated]** to **[!UICONTROL Migrated]**.

   Adobe ID users that appear in the migration tool can be migrated in this process as well. They still must login with their Adobe ID until an identity switch is performed. Contact Adobe Customer care to help with an identity switch.
