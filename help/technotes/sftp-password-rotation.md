---
title: Security Requirements For FTP And SFTP Servers
description: Learn about security requirements for FTP and SFTP servers.
feature: Data Configuration and Collection
role: Admin
---
# Security requirements for FTP and SFTP servers

This page covers security requirements for existing FTP and SFTP servers that receive data delivered by Adobe Analytics Data Feeds or Data Warehouse.

* **Existing FTP servers**: Must be upgraded to use SFTP, as described in the section below, [Upgrade FTP servers to use SFTP](#upgrade-ftp-servers-to-use-sftp).

  This upgrade must be completed by < **_Date???_** >.

* **Existing SFTP servers (and newly upgraded SFTP servers)**: Must have old passphrases rotated, as described in the section below, [Rotate your SFTP passphrase](#rotate-your-sftp-passphrase).

  Regular rotation of the SFTP passphrase is a security best practice that helps protect your data.

>[!IMPORTANT]
>
>Consider the following situations before completing the steps in this article.
>
>* **Adobe recommends transitioning to a modern cloud destination rather than upgrading to SFTP, if possible.**
>FTP and SFTP are legacy destination types. Rather than upgrading FTP accounts to SFTP and rotating SFTP passphrases as described in this article, Adobe recommends moving to a modern cloud destination type (such as Amazon S3, Google Cloud Platform, or Azure). These cloud destinations provide a higher level of security. For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts). 
>
>* **If FTP and SFTP accounts are used exclusively for Classifications, migrate to Classification sets.** 
>If your FTP or SFTP account is used exclusively for Classifications, you should migrate from the **Classifications importer** to **Classification sets**, rather than upgrading FTP accounts to SFTP and rotating SFTP passphrases as described in this article. The Classification importer will be deprecated and no longer accessible after **August 31, 2026**. For more information, see [Classification sets overview](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview). 

## Upgrade FTP servers to use SFTP

>[!IMPORTANT]
>
>If your FTP data is delivered to a third-party partner (for example, a consulting firm or analytics vendor), coordinate with them before following the steps in this article. 


### Step 1: Generate your organization's download key and add it to your FTP server

This section describes how to:

* Generate your organization's **download key**. This is a public/private key pair that is used by your organization to _download_ data from the FTP server. 

  >[!NOTE]
  >
  >In a future step, you will download Adobe's **upload key** (the public portion). This is a second public/private key pair that is used by Adobe to _upload_ data to the FTP server.

* Add the public key to your existing FTP server. 

To set up secure transfer for downloading data from your FTP server: 

1. Log in to the workstation where you download data from the FTP server.

1. Generate a public/private key pair to use for secure transfer:
   
   * **In a Linux environment**: Run the following command to generate the ed25519 key pair: 

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     If your policy does not allow you to use ed25519 keys, run the following command to generate the RSA key pair (**Note:** The RSA key typically applies to customers who operate under FIPS 186-4, as ed25519 is first supported in the newer FIPS 186-5):

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **In a Windows environment**: Use PuTTYgen.

1. Create a file named [!DNL `authorized_keys`] (no extension).

1. Copy the contents of the public key into the [!DNL `authorized_keys`] file.

1. Upload the [!DNL `authorized_keys`] file to your FTP server:

    1. Connect to the FTP server and log in with your username and password.    
       This can be an Adobe-hosted FTP server or your own FTP server. 
    1. Create a [!DNL .ssh] directory (if it does not already exist).
    1. Upload the [!DNL `authorized_keys`] file to the [!DNL .ssh] directory.

1. Update your firewall settings to allow inbound connections from Adobe's IP ranges on port 22. <_**should this go here? I also have it later**_>

   Port 22 is the standard port for SFTP connections.

1. Test the connection by logging in to the server using SFTP. <_**or, "by accessing the server using your SSH keys?**_>

### Step 2: Create a new SFTP location account in Adobe Analytics

Create a new SFTP location account to replace each existing FTP account. 

When creating a new SFTP location account, you must use the same hostname, username, and passphrase (if one exists)< **_is this correct?_** > that are used in the existing FTP account it is replacing.

>[!NOTE]
>
>In a future step, you will configure this new location account to be used as the destination for your Data Feeds and Data Warehouse deliveries.  

#### Inventory your FTP accounts 
 
Identify all FTP accounts that are receiving data for Data Feeds or Data Warehouse. This information is shown in your FTP configuration settings, as described in the [Legacy account types](/help/components/locations/configure-import-accounts.md#configure-a-location-account) section of the article [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md). 
 
For each account, gather the following information: 
 
* **Host**: The hostname of the FTP server your account connects to (for example, `ftp.omniture.com`, `ftp2.omniture.com`, and so forth). 
 
* **Port**: SFTP clients connect on port 22. FTP connections that are non-secure use port 21. 
 
* **Username**: The username used to log in to the FTP server. 
 
* **Location account secret**: The current account secret for the account. This is the account secret (password) that you use currently when downloading data delivered to your FTP location. This information is not available from the Adobe Analytics interface. 

#### Confirm that you can update credentials in your tools 
 
Make sure you can update the FTP account secret in whatever tool or script you use to connect to the FTP site (for example, an FTP client, automated script, or third-party platform). 

#### Create the SFTP account

1. In Adobe Analytics, go to [!UICONTROL **Components**] > [!UICONTROL **Locations**]. 
 
1. Select the [!UICONTROL **Location accounts**] tab. 
 
1. Select [!UICONTROL **Add account**]. 
 
1. In the [!UICONTROL **Account type**] drop-down field, select [!UICONTROL **SFTP (legacy)**]. 
 
1. Complete the following fields: 

   | Field name | Function |
   |---------|----------|
   | [!UICONTROL **Hostname**] |  Your SFTP hostname (for example, `sftp.omniture.com`). | 
   | [!UICONTROL **Port**] | The firewall port through which data will be sent. This is port 22 for SFTP connections. |
   | [!UICONTROL **Username**] | Your SFTP username. Use the same username that you used for your FTP account. |
   | **Passphrase** | < **_not sure about this. It's not a field in the UI? How do they configure the passphrase? The FTP account contains an account secret. Does that become the passphrase?_** > |
 
1. Select [!UICONTROL **Save**]. 

1. In the [!UICONTROL **Account created**] dialog, download the RSA or ed25519 public key, then select **[!UICONTROL OK]**. This is the public key that is used by Adobe to upload data to the SFTP server. (You will use this key in the following section, [Add the Adobe upload key to the SFTP server](#add-the-adobe-upload-key-to-the-sftp-server).)

1. Repeat this process for each SFTP account you want to create. 

1. Continue with the following section, [Upload the public key to the SFTP server](#upload-the-public-key-to-the-sftp-server).

#### Add the Adobe upload key to the SFTP server

The public key you just downloaded in Step 7 of the previous section is Adobe's **upload key**. This is a public/private key pair that is used by Adobe to _upload_ data to the SFTP server. 

You need to add this public key to the same `authorized_keys` file where you previously added your organization's download key (the one you generated in [Step 1: Generate your organization's download key and add it to your FTP server](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server)).

To add Adobe's upload key to the SFTP server:

1. Connect to the SFTP server and log in, either by using your username and password or by using SFTP.

   This can be an Adobe-hosted SFTP server or your own SFTP server.

1. Open the [!DNL `authorized_keys`] file in the [!DNL .ssh] directory. This file should already contain your organization's download key from [Step 1](#step-1-generate-a-publicprivate-key-pair-and-upload-the-public-key-to-your-existing-ftp-server). Add Adobe's upload key to this same file.

1. Repeat this process for each SFTP account that you created in the previous section, [Create the SFTP account](#create-the-sftp-account).

1. Continue with the following section, [Add a location within the account](#add-a-location-within-the-account).
 
#### Add a location within the account 
 
1. On the **Locations** tab, select **Add location**. 
 
1. Specify a name, description, and whether this location will be used with Data Feeds or Data Warehouse. 
 
1. In the [!UICONTROL **Location account**] field, select the account you just created. 
 
1. In the [!UICONTROL **Directory path**] field, specify the path to the directory on the SFTP server. Folders in the path must already exist; otherwise, an error occurs. For example, `/folder_name/folder_name`. 
 
1. Select **Save**. 
 
1. Repeat this process for each SFTP account you created. 
 
For detailed instructions, see [Configure cloud import and export locations](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations).

### Step 3: Edit Data Feeds and Data Warehouse requests to use the new SFTP destination
 
Update any existing scheduled Data Feeds and Data Warehouse requests that currently send data to FTP destinations to use the new SFTP destinations you created. 

#### Edit Data Feeds

Edit each scheduled data feed that is configured with the old FTP destination to use the new SFTP destination:

1. In Adobe Analytics, select [!UICONTROL **Admin**] > [!UICONTROL **Data feeds**].

1. Locate the data feed that you want to edit. To locate a data feed, you can [filter and search the list of data feeds](#filter-and-search-the-list-of-data-feeds).

1. Select the data feed in the [!UICONTROL **Feed name**] column.

   The [!UICONTROL **Edit _feed_name_**] page is displayed.

1. In the [!UICONTROL **Destination**] section, in the [!UICONTROL **Account**] field, use the drop-down menu to select the new SFTP destination that you created.

1. In the [!UICONTROL **Location**] field, use the drop-down menu to select the location in the SFTP account.

1. Select [!UICONTROL **Save**].

For more detailed information, see [Edit a data feed](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).

#### Edit Data Warehouse requests

Edit each scheduled Data Warehouse request that is configured with the old FTP destination to use the new SFTP destination:

1. In Adobe Analytics, select [!UICONTROL **Tools**] > [!UICONTROL **Data Warehouse**].

1. On the Data Warehouse page, select the request that you want to edit.

   ![Manage a request](assets/dw-manage-request.png)

1. Select [!UICONTROL **Edit**]. 

1. Select the [!UICONTROL **Report destination**] tab.

1. In the [!UICONTROL **Account**] field, use the drop-down menu to select the new SFTP destination that you created.

1. In the [!UICONTROL **Location**] field, use the drop-down menu to select the location in the SFTP account.

1. Select [!UICONTROL **Save changes**].

 For more detailed information, see [Edit requests](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) in [Manage Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md).

### Step 4: Update your firewall settings

1. (Required) Update your firewall settings to allow inbound connections from Adobe's IP ranges on port 22. 

   Port 22 is the standard port for SFTP connections.

2. (Recommended) Remove old FTP-specific rules, such as allowing inbound connections on port 21. 

   FTP uses port 21, plus a range of additional ports for data transfer. As a security best practice, you should eventually remove this unnecessary access through your firewall.

### Step 5: Ensure that scheduled Data Feeds and Data Warehouse requests are being delivered correctly 
 
After updating each existing Data Feed and Data Warehouse request to use the new SFTP account and location, wait for the next scheduled delivery. Verify that data arrives at the new destination as expected. 

### Step 6: Rotate the passphrase on the upgraded SFTP server

After upgrading an FTP server to SFTP, you must also rotate the SFTP passphrase, as described in the following section, [Rotate your SFTP passphrase](#rotate-your-sftp-passphrase). 

## Rotate your SFTP passphrase

An SFTP passphrase serves as a fallback authentication method if key-based authentication fails. 

Rotate the SFTP passphrase soon after upgrading from FTP to SFTP. It should continue to be rotated on a regular schedule< **_How often?_** >.   

1. Contact Adobe Customer Care and request a new passphrase.
 
1. For each SFTP account, provide the **Hostname** and **Username**. 
 
   Customer Care will generate a new passphrase for each FTP account. 


<!--
< **_Ignore everything after this_** >

-------

## Set up a new SFTP server or upgrade your existing FTP server

## Upgrade your FTP server to use SFTP where files are delivered or FTP account to use SFTP

Set up an SFTP server where Data Feed and Data Warehouse files can be delivered. This could beYou first need to upgrade your FTP server to use SFTP To upgrade an FTP account to use SFTP, follow the steps in [Connect to an FTP account with SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md).

## Create an SFTP account

## Rotate the passphrase on SFTP accounts


 
Adobe recommends that you periodically rotate the account secrets (passwords) on your FTP accounts that are associated with Data Feeds and Data Warehouse. 
 
Regular rotation of account secrets is a security best practice that helps protect your data. 
 
To ensure uninterrupted reception of data, follow the steps in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets) prior to changing any account secrets.  
 
>[!IMPORTANT] 
> 
>If your FTP data is delivered to a third-party partner (for example, a consulting firm or Adobe Analytics vendor), coordinate with them before rotating account secrets. The third-party partner will need to update their own tools and scripts with the new account secrets immediately after the new account secrets are provided by your FTP host provider (either Adobe or another provider).

## When rotating account secrets is not necessary 
 
### Transition from FTP to a cloud destination 
 
FTP and SFTP are legacy destination types. Rather than rotating FTP account secrets, Adobe recommends moving to a modern cloud destination type (such as Amazon S3, Google Cloud Platform, or Azure), which provide a higher level of security. For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts). 
 
### Transition from the Classifications importer to Classification sets 
 
If your FTP account is used exclusively for Classifications, you should migrate from the **Classifications importer** to **Classification sets**, rather than rotating your FTP account secrets. The Classification importer will be deprecated and no longer accessible after **August 31, 2026**. For more information, see [Classification sets overview](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview). 

## Prepare to rotate account secrets 
 
Complete the following steps before attempting to rotate FTP account secrets: 
 
### Step 1: Inventory your FTP accounts 
 
Identify all FTP accounts that are receiving data for Data Feeds or Data Warehouse. This information is shown in your FTP configuration settings, as described in the [Legacy account types](/help/components/locations/configure-import-accounts.md#configure-a-location-account) section of the article [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md). 
 
For each account, gather the following information: 
 
* **Host**: The FTP destination of the host your account connects to (for example, `ftp.omniture.com`, `ftp2.omniture.com`, and so forth). 
 
* **Port**: SFTP clients connect on port 22. FTP connections that are non-secure use port 21. 
 
* **Username**: The username used to log in to the FTP site. 
 
* **location account secret**: The current account secret for the account. This is the account secret (password) that you use currently when downloading data delivered to your FTP location. This information is not available from the Adobe Analytics interface. 
 
 
### Step 2: Confirm that you can update credentials in your tools 
 
Make sure you can update the FTP account secret in whatever tool or script you use to connect to the FTP site (for example, an FTP client, automated script, or third-party platform). 
 
### Step 3: Create FTP cloud location accounts with your current credentials 
 
Create new FTP cloud location accounts to replace your existing FTP location accounts. These new accounts will be used as the destination for your Data Feeds and Data Warehouse deliveries.  
 
When creating the new FTP accounts, you must use the same hostname, username, and account secret that are used in your existing FTP accounts. 
 
#### Create each FTP account 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 
 
1. Select the **Location accounts** tab. 
 
1. Select **Add account**. 
 
1. In the **Account type** drop-down field, select **FTP (legacy)**. 
 
1. Complete the following fields: 

   | Field name | Function |
   |---------|----------|
   | **Hostname** |  Your Adobe FTP hostname (for example, `ftp.omniture.com`). | 
   | **Port** | SFTP clients connect on port 22. FTP connections that are non-secure use port 21. | 
   | **Username** | Your current FTP username. |
   | **Location account secret** | Your current FTP account secrets (password).  |
 
1. Select **Save**. 
 
Repeat this process for each FTP account. 
 
For detailed instructions, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts). 
 
#### Add a location within the account 
 
1. On the **Locations** tab, select **Add location**. 
 
1. Specify a name, description, and whether this location will be used with Data Feeds or Data Warehouse. 
 
1. In the [!UICONTROL **Location account**] field, select the account you just created. 
 
1. In the [!UICONTROL **Directory path**] field, specify the path to the directory on the FTP server. Folders must already exist; feeds throw an error if the specified path does not exist. For example, `/folder_name/folder_name`. 
 
1. Select **Save**. 
 
Repeat this process for each location. 
 
For detailed instructions, see [Configure cloud import and export locations](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations). 
 
### Step 4: Reference the new FTP cloud accounts from any scheduled Data Feeds and Data Warehouse requests 
 
Update any existing scheduled Data Feeds and Data Warehouse requests to use the FTP cloud accounts you created.  
 
* **Data Feeds**: Go to **Admin** > **Data Feeds**, edit each scheduled  Data Feed that uses an FTP account, then change the destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit a data feed](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md). 
 
* **Data Warehouse**: Go to **Tools** > **Data Warehouse**, edit each scheduled Data Warehouse request that uses an FTP account, then change the report destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit requests](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) in [Manage Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md). 
 
### Step 5: Ensure that scheduled Data Feeds and Data Warehouse requests are being delivered correctly. 
 
After updating each existing Data Feed and Data Warehouse request to use the new FTP account and location, wait for the next scheduled delivery. Verify that data arrives at the new destination as expected. 

## Request a new account secret 
 
>[!IMPORTANT] 
>
>Before requesting a new account secret, consider the following:
>
>* The steps in this section apply only if you are using an Adobe-provided FTP account. For example, the FTP hostname is `ftp.omniture.com`, `ftp2.omniture.com` or similar.   If your FTP hostname is not provided by Adobe, please contact your FTP host provider for details on changing the account secret.
> 
>* Request a new account secret only after you complete all the preparation steps described in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets). 
>
>* After Adobe Customer Care or your third-party FTP host provider provides a new account secret, the old account secret is immediately invalidated. There is no way to revert to the previous account secret. 
>
 
To request a new account secret from Adobe: 
 
1. Contact Adobe Customer Care. 
 
1. For each FTP account, provide the **Hostname** and **Username** for each account that needs a new account secret. 
 
   Customer Care will generate a new account secret for each FTP account. 

1. Continue immediately with the following section, [After you receive the new account secret](#after-you-receive-the-new-account-secret).
 
## After you receive the new account secret 
 
Act immediately after receiving the new credentials. Any delay results in failed deliveries for active Data Feeds and Data Warehouse requests. 
 
### Step 1: Update your tools and scripts 
 
Update the FTP account secret in any tool, script, or automated process that connects to the FTP account. Make sure all team members and third-party partners who access the account are notified. 
 
### Step 2: Update your cloud location accounts 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 

1. Select the **Location accounts** tab. 

1. Find the FTP account that you created in Step 3 of section, [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets).

1. Select **Edit details**. 

1. Enter the new account secret and confirm it. 

1. Select **Save**. 
 
Repeat this process for each account that was reset. 

For more detailed information about this process, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).
 
### Step 3: Test your connections 
 
Verify that your Data Feeds or Data Warehouse requests that use the FTP account are working correctly with the new account secret. 
 
>[!TIP] 
> 
>If your current tools use SFTP with SSH keys that haven't been recently rotated, consider rotating those keys as well.

 
## Troubleshooting 
 
If something goes wrong after the account secret is rotated and you cannot restore connectivity, you can create a new FTP account. After the new account is set up, point your Data Feed or Data Warehouse request to the new account and update your cloud location accordingly. 

For information about how to create an FTP account, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).

To set up secure transfer with your FTP server: 

1. Generate a public/private key pair to use for secure transfer.

   This process differs depending on whether your FTP server is Adobe-hosted or self-hosted:

   +++ For an Adobe-hosted FTP server:

   Generate a public/private key pair: 
   
      * **In a Linux environment**: Run the following command to generate the ed25519 key pair: 

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        If your policy does not allow you to use ed25519 keys, run the following command to generate the RSA key pair (**Note:** The RSA key typically applies to customers who operate under FIPS 186-4, as ed25519 is first supported in the newer FIPS 186-5):

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

      * **In a Windows environment**: Use PuTTYgen.

   +++

   +++ For a self-hosted FTP server: 
   
   If you want to set up secure transfer with your own FTP server, you must have an SFTP hostname, username, and SFTP account within Adobe Analytics that contains a valid RSA or ed25519 public key from Adobe. This key must be installed on your SFTP server. You download this public key as part of the process of [creating the SFTP account](#create-the-sftp-account).

   +++

1. Create a file named [!DNL `authorized_keys`] (no extension).



3 basic steps: Set up SFTP on customer side, then on Adobe side, then change passphrase. 

1. FTP site: ftp.omniture.com - Using username/password to connect. Adobe uses the same username/password to connect to the site.

2. user can then upload their public key to that server, then start connecting to that server with their private key using SFTP. (They also need to open Port 22 in the firewall and they would close the other ports they don't need.)

3. In Locations, create a new location, use the same username. 

4. After they create that location, we give them our public key, and they have to install it on their SFTP server.

5. Then they switch all their data feeds to use the new Location. And then we'll use SFTP to send the data. 

6. Then they call Customer Care to get new passphrase (rotate passphrase), and then they change the passphrase on their side. Passphrase is only used if SSH fails (they have the wrong keys--a bad actor could use bad keys and then use the password. But they don't have to coordinate the switching of the passphrase with installation of SFTP. )


If they're using a third-party to do this, the third-party would need to set up SFTP - This is the same as we have documented right now. It doesn't have to be immediate, though, like we were assuming before. 


If it's they're own FTP site, it would be the same. They would need to start using SFTP with their FTP server, then get our public key and install it on their server. Shouldn't matter if the FTP site is hosted by Adobe or not. 

-->

