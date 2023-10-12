---
description: Adobe supports the export of Data Warehouse requests to SFTP servers.
keywords: ftp;sftp
title: Send Data Warehouse requests to SFTP servers
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
---
# Send Data Warehouse requests to SFTP servers

Adobe supports the export of Data Warehouse requests to SFTP servers, as described in [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) in the article, [Configure a report destination for a Data Warehouse request](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).

Ensure that the following tasks are completed:

* Only port 22 is used when requesting a Data Warehouse report. 
* Adobe's `authorized_keys` file is in the `.ssh` directory within the root directory of the user you log in with.
* The destination is not to `ftp.omniture.com`. SFTP protocol between Adobe's internal servers is not supported.
* The destination supports one-factor (PKI) authentication. If there is a two-factor challenge, delivery of the report will fail. Make sure that your server is not configured to attempt two-factor authentication. Adobe Analytics requires that only the key and nothing else is used to log in.
* Adobe supports SSHv2 encryption, and falls back to SSHv1 (RSA key only).

To successfully send a Data Warehouse request via SFTP:

1. Complete the steps described in [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) in the article, [Configure a report destination for a Data Warehouse request](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), including downloading the public key.
1. Log in to the SFTP site under the same credentials that are used for the Data Warehouse request.
1. In the root directory, navigate to the folder named `.ssh` (if one does not exist, create one) and place the `authorized_keys` file there.

1. Complete the Data Warehouse request if you have not done so already, as described in [Configure a report destination for a Data Warehouse request](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).
