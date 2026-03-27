---
title: Rotate FTP Passwords for Data Feeds and Data Warehouse
description: Learn how to rotate FTP passwords for Adobe Analytics.
feature: Data Configuration and Collection
role: Admin
---
# Rotate FTP location account secrets (passwords) for Data Feeds and Data Warehouse

Adobe recommends that you periodically rotate the location account secrets (passwords) on your FTP accounts that are associated with Data Feeds and Data Warehouse.

Regular rotation of location account secrets is a security best practice that helps protect your data.

To ensure uninterrupted reception of data, follow the steps in [Prepare for password rotation](#prepare-for-password-rotation) prior to changing any location account secrets. 

>[!IMPORTANT]
>
>If your FTP data is delivered to a third-party partner (for example, a consulting firm or analytics vendor), coordinate with them before rotating location account secrets. The third-party partner will need to update their own tools and scripts with the new location account secrets immediately after the new location account secrets are provided by Adobe.

## When rotating location account secrets is not necessary

### Transition from FTP to a cloud destination

FTP and SFTP are legacy destination types. Rather than rotating FTP location account secrets, Adobe recommends moving to a modern cloud destination type (such as Amazon S3, Google Cloud Platform, or Azure), which are more secure. For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).

### Transition from the Classifications importer to Classification sets

If your FTP account is used exclusively for Classifications, you should migrate from the **Classifications importer** to **Classification sets**, rather than rotating your FTP location account secrets. Classification importer will be deprecated on **August 31, 2026**. For more information, see [Classification sets overview](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview).

## Prepare to rotate location account secrets

Complete the following steps before attempting to rotate FTP location account secrets:

### Step 1: Inventory your FTP accounts

Identify all FTP accounts that are receiving data for Data Feeds or Data Warehouse. This information is shown in your FTP configuration settings, as described in the "Legacy account types" section of the article [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md).

For each account, gather the following information:

* **Host**: The FTP destination URL of the host your account connects to (for example, `ftp.adobe.com`, `ftp2.adobe.com`, and so forth).

* **Port**: Not needed if this field is blank in your FTP account. This field is used to place feed files in a folder. Folders must already exist; feeds throw an error if the specified port does not exist.

* **Username**: The username used to log in to the FTP site.

* **location account secret**: The current location account secret for the account.


### Step 2: Confirm that you can update credentials in your tools

Make sure you can update the FTP location account secret in whatever tool or script you use to connect to the FTP site (for example, an FTP client, automated script, or third-party platform).

### Step 3: Create FTP cloud location accounts with your current credentials

FTP accounts that were created prior to October 2025 cannot be modified. If your FTP accounts were created before October 2025, create new FTP cloud location accounts to replace your existing FTP accounts. These new accounts are where you will receive Data Feeds and Data Warehouse data. 

When creating the new FTP accounts, you must use the same hostname, username, and location account secret that are used in your existing FTP accounts.

#### Create each FTP account

1. In Adobe Analytics, go to **Components** > **Locations**.

1. Select the **Location accounts** tab.

1. Select **Add account**.

1. In the **Account type** drop-down field, select **FTP (legacy)**.

1. Complete the following fields:
   * **Hostname**: Your Adobe FTP host name (for example, `ftp.omniture.com`).
   **Port**: Specify the directory path for your data stream.
   * **Username**: Your current FTP username.
   * **Location account secret**: Your current FTP location account secrets (password).

1. Select **Save**.

Repeat this process for each FTP account.

For detailed instructions, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).

#### Add a location within the account

1. On the **Locations** tab, select **Add location**.

1. Specify a name, description, and whether this location will be used with Data Feeds or Data Warehouse.

1. In the [!UICONTROL **Location account**] field, select the location with the account you just created.

1. In the [!UICONTROL **Directory path**] field,  specify the path to the directory on the FTP server. Folders must already exist; feeds throw an error if the specified path does not exist. For example, `/folder_name/folder_name`.

1. Select **Save**.

Repeat this process for each location.

For detailed instructions, see [Configure cloud import and export locations](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations).

### Step 4: Reference the new cloud locations from each Data Feeds and Data Warehouse request

Update each existing Data Feed and Data Warehouse request to use the FTP cloud location you created. 

* **Data Feeds**: Go to **Admin** > **Data Feeds**, edit each feed that uses the FTP accounts, and change the destination to the new FTP cloud location.

  For detailed instructions, see [Edit a data feed](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).

* **Data Warehouse**: When you next schedule or edit a Data Warehouse request, select the new FTP cloud location as the report destination.

  For detailed instructions, see [Edit requests](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) in [Manage Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md).

## Request a new location account secret

Request a new location account secret from Adobe only after you complete all the preparation steps described in [Prepare to rotate location account secrets](#prepare-to-rotate-location-account-secrets).

>[!IMPORTANT]
>
>After Adobe Customer Care provides a new location account secret, the old location account secret is immediately invalidated. There is no way to revert to the previous location account secret.

To request a new location account secret:

1. Have a supported user in your organization contact **Adobe Customer Care**.

1. For each FTP account, provide the **Hostname**, **Port**, **username**, and **location account secret** for each account that needs a new location account secret.

1. Customer Care will generate a new location account secret for each account.

## After you receive the new location account secret

Act immediately after receiving the new credentials. Any delay will result in failed deliveries for active Data Feeds and Data Warehouse requests.

### Step 1: Update your tools and scripts

Update the FTP location account secret in any tool, script, or automated process that connects to the FTP account. Make sure all team members and third-party partners who access the account are notified.

### Step 2: Update your cloud location accounts

1. In Adobe Analytics, go to **Components** > **Locations**.
2. Select the **Location accounts** tab.
3. Find the FTP account you created in Step 4, and select **Edit details**.
4. Enter the new location account secret and confirm it.
5. Select **Save**.

Repeat for each account that was reset.

### Step 3: Test your connections

Verify that your Data Feeds or Data Warehouse requests that use the FTP account are working correctly with the new location account secret.

>[!TIP]
>
>If your current tools use SFTP with SSH keys, consider rotating those keys as well if they haven't been rotated recently.

## Troubleshooting

If something goes wrong after the location account secret is rotated and you cannot restore connectivity, you can create a new FTP account. After the new account is set up, point your Data Feed or Data Warehouse request to the new account and update your cloud location accordingly.
