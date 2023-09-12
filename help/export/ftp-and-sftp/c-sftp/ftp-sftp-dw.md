---
description: Adobe supports the export of Data Warehouse requests to SFTP servers.
keywords: ftp;sftp
title: Send Data Warehouse requests to SFTP servers
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
---
# Send Data Warehouse requests to SFTP servers

Adobe supports the export of Data Warehouse requests to SFTP servers.

Ensure that the following tasks are completed:

Adobe supports the export of Data Warehouse requests to SFTP servers, provided the following are met:

* `sftp://` protocol is specified in the host field (for example, `sftp://ftp.example.com`) and ONLY port 22 is used when requesting a Data Warehouse report. You can also use the `sftp+norename://` option, as described below.
* Adobe's `authorized_keys` file is in the `.ssh` directory within the root directory of the user you log in with
* The destination is not to `ftp.omniture.com`. SFTP protocol between Adobe's internal servers is not supported.
* The destination supports one-factor (PKI) authentication. If there is a two-factor challenge, delivery of the report will fail. Make sure that your server is not configured to attempt two-factor authentication. Adobe Analytics requires that only the key and nothing else is used to log in.
* Adobe supports SSHv2 encryption, and falls back to SSHv1 (RSA key only).

To successfully send a Data Warehouse request via SFTP:

1. Obtain the `authorized_keys` file by having one of your organization's supported users contact Customer Care.
1. After this file is obtained, log in to the FTP site under the same credentials that are used for the Data Warehouse request.
1. In the root directory, navigate to the folder named `.ssh` (if one does not exist, create one) and place the `authorized_keys` file there.

1. Go to the Data Warehouse request manager. Configure the request as desired, then click **[!UICONTROL Advanced Delivery Options]**.

1. In the pop-up window, click **[!UICONTROL FTP]**, then specify the ftp site (including the `sftp://` protocol, such as `sftp://ftp.omniture.com`) via port 22.

   Including the `sftp://` protocol is only permitted when using SFTP. Regular FTP requests should omit the protocol prefix (such as, `ftp.omniture.com` instead of `ftp://ftp.omniture.com`).

1. Enter the name of the folder you want to place the file in the Folder field. A folder is required.
1. Enter the same username and password used in Step 2.
1. Click **[!UICONTROL Send]**.

The sftp PUT command places a temporary file with an extension of .part in the specified directory. When the upload completes the file extension is renamed to the final extension, at which point it is ready for your use.

Alternatively, `sftp+norename://` can be specified instead of `sftp://` to upload the file directly with the final name, without a temporary `.part` file name during upload. This approach is appropriate when the SFTP server handles file renaming during upload automatically, and there is no chance of the file being processed before upload is complete.
