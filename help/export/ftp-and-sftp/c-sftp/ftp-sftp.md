---
description: SFTP is a secure protocol for transferring data that ensures that nobody can see your data but you. Adobe Engineering Services can set up an SFTP account to securely retain your data.
keywords: ftp;sftp
title: Secure File Transfer Protocol - overview
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
---
# Secure File Transfer Protocol - overview

SFTP is a secure protocol for transferring data that ensures that nobody can see your data but you. Adobe Engineering Services can set up an SFTP account to securely retain your data.

## Push Delivery {#section_A47831BB1DCA490BB57F0940617AA506}

This means that Adobe's servers "push" the file to your servers. Essentially, we deliver it to your end point.

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) and [Analytics Data Feed](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html) can push data via SFTP.

The following Analytics tools **cannot** push data via SFTP:

* Reports & Analytics 
* Ad Hoc Analysis 
* Report Builder

## Pull Delivery {#section_FA29FAEF02FE40B8B32452146A036F48}

This means that the file is sent to one of Adobe's servers using normal FTP. If you want the file on your server, you have to pull it off Adobe's server using SFTP from your server to Adobe's FTP server. You can do this using one of three methods:

* [Connect to Adobe via SFTP without a password.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md) 
* [Connect to an Adobe FTP Account with SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md) 
* You can push any reports you want to Adobe's FTP-like data feeds/R&A/Ad Hoc, and so on and then Pull them off. Adobe cannot deliver these reports to the SFTP server you have set up.
