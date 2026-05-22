---
title: Security Requirements for FTP and SFTP Servers
description: Learn about security requirements for FTP and SFTP servers.
feature: Data Configuration and Collection
role: Admin
TQID: 'https://experienceleague.adobe.com/qbBCeUihfvRTQm7LvR8jylRWf8rRlzFoZfs62l0fito'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
---
# Security requirements for FTP and SFTP servers

This page covers security requirements for existing FTP and SFTP servers that receive data delivered by Adobe Analytics Data Feeds or Data Warehouse.

* **Existing FTP servers**: Must be upgraded to use SFTP, as described in the section below, [Upgrade FTP servers to use SFTP](#upgrade-ftp-servers-to-use-sftp).

  Upgrading from FTP to SFTP is a requirement because SFTP allows for increased security.

  Alternatively, for a higher level of security, you can transition to a modern cloud destination. (For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).)

* **Existing SFTP servers (and newly upgraded SFTP servers)**: Must have old passwords rotated, as described in the section below, [Rotate your SFTP password](#rotate-your-sftp-password).

  Regular rotation of the SFTP password is a security best practice that helps protect your data.

>[!IMPORTANT]
>
>Consider the following situations before completing the steps in this article.
>
>* **Adobe recommends transitioning to a modern cloud destination rather than upgrading to SFTP, if possible.**
>FTP and SFTP are legacy destination types. Rather than upgrading FTP accounts to SFTP and rotating SFTP passwords as described in this article, Adobe recommends moving to a modern cloud destination type (such as Amazon S3, Google Cloud Platform, or Azure). These cloud destinations provide a higher level of security. For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).
>
>* **If FTP and SFTP accounts are used exclusively for Classifications, migrate to Classification sets.**
>If your FTP or SFTP account is used exclusively for Classifications, you should migrate from the **Classifications importer** to **Classification sets**, rather than upgrading FTP accounts to SFTP and rotating SFTP passwords as described in this article. The Classification importer will be deprecated and no longer accessible after **August 31, 2026**. For more information, see [Classification sets overview](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview).

## Prerequisites

### Inventory your FTP accounts

You must complete the SFTP upgrade steps on this page for every FTP site used with Data Feeds or Data Warehouse.

As such, you must identify all FTP accounts that are receiving data for Data Feeds or Data Warehouse. This information is shown in your FTP configuration settings, as described in the [Legacy account types](/help/components/locations/configure-import-accounts.md#configure-a-location-account) section of the article [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md).

For each account, gather the following information:

* **Host**: The hostname of the FTP server your account connects to (for example, `ftp.omniture.com`, `ftp2.omniture.com`, and so forth).

* **Port**: When using an Adobe-hosted SFTP server, SFTP clients connect on port 22. FTP connections that are non-secure use port 21.

* **Username**: The username used to log in to the FTP server.

* **Location account secret**: The current account secret for the account. This is the account secret (password) that you use currently when downloading data delivered to your FTP location. This information is not available from the Adobe Analytics interface.

### Confirm that you can update credentials in your tools

Make sure you can update the SFTP passwords in whatever tool or script you use to connect to the SFTP site (for example, an SFTP client, automated script, or third-party platform).

All clients should connect via SFTP with password as a fallback.

## Upgrade FTP servers to use SFTP

>[!IMPORTANT]
>
>If your FTP data is delivered to a third-party partner (for example, a consulting firm or analytics vendor), coordinate with them before following the steps in this article.

### Step 1: Generate your organization's SSH keys for downloading data

This section describes how to generate your organization's SSH keys (a public/private key pair) that are used to **download data** from the SFTP server.

  >[!NOTE]
  >
  >In a future step, you will download another public key provided by Adobe. This is part of a second public/private key pair, which is used by Adobe to **upload data** to the SFTP server.

To set up secure transfer for downloading data from your FTP server:

1. Log in to the workstation where you download data from the FTP server.

1. Generate a public/private key pair to use for secure transfer.

   When using an Adobe-hosted SFTP server, Adobe supports RSA and ed25519 keys.

   * **In a Linux environment**: Run the following command to generate the ed25519 key pair:

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     If your policy does not allow you to use ed25519 keys, run the following command to generate the RSA key pair:

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **In a Windows environment**: Use PuTTYgen.

1. Create a file named [!DNL `authorized_keys`] (no extension).

1. Copy the contents of the public key into the [!DNL `authorized_keys`] file.

1. In a future step, you will come back to this [!DNL `authorized_keys`] file to add Adobe's public key, which is used by Adobe to upload data to the SFTP server. Then you will add the [!DNL `authorized_keys`] file to the SFTP server.

### Step 2: Create a new SFTP location account in Adobe Analytics

Create a new SFTP location account to replace each existing FTP account.

When creating a new SFTP location account, you must use the same hostname and username that are used in the existing FTP account it is replacing.

>[!NOTE]
>
>In a future step, you will configure this new location account to be used as the destination for your Data Feeds and Data Warehouse deliveries.

#### Create the SFTP account

1. In Adobe Analytics, go to [!UICONTROL **Components**] > [!UICONTROL **Locations**].

1. Select the [!UICONTROL **Location accounts**] tab.

1. Select [!UICONTROL **Add account**].

1. In the [!UICONTROL **Account type**] drop-down menu, select [!UICONTROL **SFTP (legacy)**].

1. Complete the following fields:

   | Field name | Function |
   |---------|----------|
   | [!UICONTROL **Hostname**] | Your SFTP hostname (for example, `ftp.omniture.com`). |
   | [!UICONTROL **Port**] | The firewall port through which data will be sent. This is port 22 for Adobe-hosted SFTP connections. |
   | [!UICONTROL **Username**] | Your SFTP username. Use the same username that you used for your FTP account. |

1. Select [!UICONTROL **Save**].

1. In the [!UICONTROL **Account created**] dialog, download the RSA or ed25519 public key, then select [!UICONTROL **OK**]. This is the SSH public key that is used by Adobe to upload data to the SFTP server. (You will use this key in the following section, [Add Adobe's SSH public key to the SFTP server](#add-adobes-ssh-public-key-to-the-sftp-server).)

1. Repeat this process for each SFTP account you want to create.

1. Continue with the following section, [Upload the public key to the SFTP server](#upload-the-public-key-to-the-sftp-server).

#### Add Adobe's SSH public key to the [!DNL `authorized_keys`] file and upload it to your FTP server

The public key you just downloaded in Step 7 of the previous section is part of a public/private key pair that is used by Adobe to **upload data** to the SFTP server.

You need to add this public key to the same [!DNL `authorized_keys`] file where you previously added your organization's download key (the one you generated in [Step 1: Generate your organization's SSH keys for downloading data](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)).

To add Adobe's SSH public key to the [!DNL `authorized_keys`] file and upload it to your FTP server:

1. Log in to the workstation where you download data from the FTP server.

1. Open the [!DNL `authorized_keys`] file and add Adobe's upload key to it. This file should already contain your organization's download key from [Step 1: Generate your organization's SSH keys for downloading data](#step-1-generate-your-organizations-ssh-keys-for-downloading-data).

1. Upload the [!DNL `authorized_keys`] file to your FTP server:

    1. Connect to the FTP server and log in with your username and password.
       This can be an Adobe-hosted FTP server or your own FTP server.
    1. Create a [!DNL .ssh] directory (if it does not already exist).
    1. Upload the [!DNL `authorized_keys`] file to the [!DNL .ssh] directory.

1. Update your firewall settings to allow inbound connections from the SFTP server. When using an Adobe-hosted SFTP server, allow inbound connections from Adobe's IP ranges on port 22.

1. Test the connection by logging in to the server using your SFTP client.

1. Repeat this process for each SFTP account that you created in the previous section, [Create the SFTP account](#create-the-sftp-account).

1. Continue with the following section, [Add a location within the account](#add-a-location-within-the-account).

#### Add a location within the account

1. On the [!UICONTROL **Locations**] tab, select [!UICONTROL **Add location**].

1. Specify a name, description, and whether this location will be used with Data Feeds or Data Warehouse.

1. In the [!UICONTROL **Location account**] field, select the account you just created.

1. In the [!UICONTROL **Directory path**] field, specify the path to the directory on the SFTP server. Folders in the path must already exist; otherwise, an error occurs. For example, `/folder_name/folder_name`.

1. Select [!UICONTROL **Save**].

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

If you haven't already, you need to update your firewall settings, as follows:

* **When using Adobe's FTP servers**: You need to update your firewall settings to allow **outbound** connections on port 22.

* **When using your own FTP server**: You need to update your firewall settings to allow **inbound** connection on whatever port you are hosting the service, which is typically port 22.

You should also remove old FTP-specific rules, such as allowing inbound connections on port 21. (FTP uses port 21, plus a range of additional ports for data transfer. As a security best practice, you should eventually remove this unnecessary access through your firewall.)

### Step 5: Ensure that scheduled Data Feeds and Data Warehouse requests are being delivered correctly

After updating each existing Data Feed and Data Warehouse request to use the new SFTP account and location, wait for the next scheduled delivery. Verify that data arrives at the new destination as expected.

### Step 6: Rotate the password on the upgraded SFTP server

After upgrading an FTP server to SFTP, you must also rotate the SFTP password, as described in the following section, [Rotate your SFTP password](#rotate-your-sftp-password).

## Rotate your SFTP password

An SFTP password serves as a fallback authentication method if key-based authentication fails.

Rotate the SFTP password soon after upgrading from FTP to SFTP. It should continue to be rotated on a regular schedule, according to your established policies.

1. Contact Adobe Customer Care and request a new password.

1. For each SFTP account, provide the **Hostname** and **Username**.

   Customer Care will generate a new password for each FTP account.

1. Update the password in whatever client you use to connect to the SFTP server.


