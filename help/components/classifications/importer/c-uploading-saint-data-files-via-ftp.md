---
description: How to upload data files via FTP.
title: FTP import
feature: Classifications
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
---
# FTP import (legacy)

>[!IMPORTANT]
>
>Adobe no longer recommends using FTP for import as described on this page. 
>
>FTP is not recommended because it is an unencrypted method of sharing files, which means that anyone can intercept the file contents as well as the username and password used for the account. 
>
>Instead, configure a cloud account as described in [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md).

Steps that describe how to upload data files via FTP.

## FTP import {#concept_2F965BE873254546A61FB755F25299FD}

To upload data files via FTP:

1. **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

The following recommended limits are important.

>[!IMPORTANT]
>
>Having too many small files or single large files can create unnecessary processing load on processing servers. Adobe recommends splitting large files into 50 MB chunks, and combining small files together.

The initial setup populates the classifications database with a large set of original data, or restructures the classifications, rather than reclassifying a few rows or adding rows.

Following an initial upload in a report suite (for a given variable or report), Adobe recommends uploading only new and updated rows in subsequent imports. Rows that are not being changed should be omitted from future uploads.

Each new key value you upload counts against your uniques for that variable for the month.

If you have exceeded your uniques for the month, you will not see the corresponding classifications data for the uniques exceeded values in reporting. You can see those classifications in Data Warehouse.

>[!NOTE]
>
>The time required to process a classification data file varies on the size of the file and the current number of files already being processed by Adobe's servers. Processing of data files usually takes no longer than 72 hours.

## Create an FTP account

Before uploading data via FTP, create an FTP account. >

See [FTP and sFTP](/help/export/ftp-and-sftp/ftp-overview.md) for additional details on Adobe FTP servers.

1. Click **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. On the **[!UICONTROL Import File]** tab, click **[!UICONTROL Add New]**.
1. Specify the FTP account details:

   |  Element  | Description  |
   |---|---|
   |  **Name**  | The FTP account name.  |
   |  **Data Set to be Classified**  | From the drop-down list, select the data set (marketing report variable) that you want to classify.  |
   |  **Select Report Suites**  | Select the report suites where you want to classify the selected data set. To select multiple report suites, the classifications for each of the selected report suites must be identical.  |
   |  **Overwrite Data on Conflicts**  | Select this option to overwrite duplicate data. This option is useful if you are updating existing classifications. If you are on the [latest classification architecture](../sets/overview.md), this setting is always enabled. |
   |  **After Import is Complete**  | Select this option to automatically export the updated data set to the same FTP account once Specify the email address to receive notifications about this FTP account once the import is complete. If you are on the [latest classification architecture](../sets/overview.md), this option is unavailable.  |
   |  **Notification Recipient**  | Specify the email address to receive notifications about this FTP account.  |
   |  **Authorize**  | (Required) Authorizes Adobe to automatically import all data files sent to the new FTP account.  |

1. Click **[!UICONTROL Save]**.

Once created, you can edit or delete FTP accounts by clicking the appropriate link next to the desired FTP account.

>[!NOTE]
>
>Notifications are not sent if an import introduces no changes to a classification. An email is only sent if it is successful and results in changes to a classification.

## Import classifications via FTP

You can use an FTP account to import classifications into Adobe Analytics.

To import classifications via FTP:

1. Click **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1. Use the FTP access information (Host, Login, Password) to access the FTP server using an FTP client of your choosing.
1. Upload the data file ( `.tab` or `.txt`) to the FTP server.
1. After uploading the data file, upload a FIN file that indicates the file is ready to process.

   The FIN file is an empty file that has the same name as your data file, with a `.fin` filename extension. For example, if your data file is `classdata1.tab`, the FIN filename is `classdata1.fin`.

At regular intervals, Adobe retrieves uploaded data files that have an associated FIN file. Adobe imports them into the report suites and data sets specified in the FTP account configuration.

Once Adobe Analytics has read and processed files uploaded in the FTP folder, the files are then automatically removed off the FTP site.
