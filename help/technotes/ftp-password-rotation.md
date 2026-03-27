---
title: Rotate FTP Passwords for Adobe Analytics
description: Learn how to rotate FTP passwords for Adobe Analytics.
feature: Data Configuration and Collection
role: Admin
---
# Rotate FTP passwords for Adobe Analytics

Adobe recommends that you periodically rotate the passwords on your FTP accounts, which can be associated with Data Feeds, Data Warehouse, and Classifications. 

Regular password rotation is a security best practice that helps protect your data.

You must complete the prerequisites before rotating FTP passwords.

>[!NOTE]
>
>Consider the following when rotating FTP passwords:
>
>* FTP and SFTP are legacy destination types. Rather than rotating FTP passwords, Adobe recommends moving to a modern cloud destination type (such as Amazon S3, Google Cloud Platform, or Azure), which are more secure. For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).
>
>* If your FTP data is delivered to a third-party partner (for example, a consulting firm or analytics vendor), coordinate with them before continuing with the password rotation process. The third-party partner will need to update their own tools and scripts with the new password immediately after the reset.

## Prerequisites

Complete the following steps before attempting to rotate FTP passwords.

### Step 1: Inventory your FTP accounts

Identify all FTP accounts associated with your Adobe Analytics implementation. For each account, gather the following information:

* **FTP host name**: The Adobe host your account connects to (for example, `ftp.omniture.com`, `ftp2.omniture.com`, or another Adobe-hosted FTP endpoint such as `ftp3`, `ftp4`, or `ftp5`).
* **Username**: The username used to log in to the FTP site.
* **Account secret / password**: The current password for the account.
* **How the account is used**: Determine whether each account is used for Data Feeds, Data Warehouse, Classifications, or a combination.

### Step 2: Identify the destination path for each data stream

For each active Data Feed or Data Warehouse request that uses FTP, note the directory path where files are delivered. You'll need this when you configure a cloud location later in the process.

### Step 3: Confirm that you can update credentials in your tools

Make sure you have the ability to update the FTP password in whatever tool or script you use to connect to the FTP site (for example, an FTP client, automated script, or third-party platform).

### Step 4: Create a cloud location account with your current credentials

Before the password changes, create a cloud location account using your existing FTP credentials so you can centrally manage your connection details going forward. This also makes it faster to update credentials after the reset.

To create the account:

1. In Adobe Analytics, go to **Components** > **Locations**.
2. Select the **Location accounts** tab.
3. Select **Add account**.
4. In the **Account type** drop-down, select **FTP** (under legacy account types).
5. Fill in the following fields:
   * **Host** — Your Adobe FTP host name (for example, `ftp.omniture.com`).
   * **Username** — Your current FTP username.
   * **Password** — Your current FTP password.
6. Select **Save**.

Then add a location within that account:

1. On the **Locations** tab, select **Add location**.
2. Associate the location with the account you just created.
3. In the **Path** field, enter the directory path for your data stream.
4. Select **Save**.

Repeat this for each FTP account and destination path combination.

For detailed instructions, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts) and [Configure cloud import and export locations](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations).

### Step 5: Point your Data Feeds and Data Warehouse requests to the new cloud locations

Update each existing Data Feed and Data Warehouse request to use the cloud location you created in Step 4 rather than a legacy inline FTP destination. This ensures that when the password is reset, you only need to update it in one place (the location account) instead of in every individual feed or request.

* **Data Feeds** — Go to **Admin** > **Data Feeds**, edit each feed, and change the destination to the cloud location.
* **Data Warehouse** — When you next schedule or edit a Data Warehouse request, select the cloud location as the report destination.

### Step 5a: If FTP is used only for Classifications

If your FTP account is used exclusively for Classifications import, you do not need to create a cloud location for it. Instead, Adobe recommends migrating to **Classification sets**, which provide a more modern and streamlined classification management experience.

>[!IMPORTANT]
>
>The Classification importer will be deprecated on **August 31, 2026**. After that date, you will no longer be able to import classifications using FTP. Migrate to Classification sets before this date to ensure continued functionality. For more information, see [Classification sets overview](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview).

## Request the password reset

Once you have completed all the preparation steps above:

1. Have a supported user in your organization contact **Adobe Customer Care**.
2. Provide the **FTP host name** and **username** for each account that needs a new password.
3. Customer Care will generate a new password for each account.

>[!IMPORTANT]
>
>Once Customer Care resets the password, the old password is immediately invalidated. There is no way to revert to the previous password.

## After you receive the new password

Act immediately after receiving the new credentials. Any delay will result in failed deliveries for active Data Feeds and Data Warehouse requests.

### Step 7: Update your tools and scripts

Update the FTP password in any tool, script, or automated process that connects to the FTP account. Make sure all team members and third-party partners who access the account are notified.

### Step 8: Update your cloud location accounts

1. In Adobe Analytics, go to **Components** > **Locations**.
2. Select the **Location accounts** tab.
3. Find the FTP account you created in Step 4, and select **Edit details**.
4. Enter the new password and confirm it.
5. Select **Save**.

Repeat for each account that was reset.

### Step 9: Test your connections

Verify that all Data Feeds, Data Warehouse requests, and any other processes that use the FTP account are working correctly with the new password.

>[!TIP]
>
>If your current tools use SFTP with SSH keys, consider rotating those keys as well if they haven't been rotated recently.

## Troubleshooting

If something goes wrong after the password rotation and you cannot restore connectivity, you can request that Adobe Customer Care create a new FTP account as a fallback. Once the new account is set up, point your feeds and requests to the new account and update your cloud location accordingly.
