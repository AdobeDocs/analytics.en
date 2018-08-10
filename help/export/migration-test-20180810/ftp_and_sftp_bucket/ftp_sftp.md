---
description: SFTP is a secure protocol for transferring data that ensures that nobody can see your data but you. Adobe Engineering Services can set up an SFTP account to securely retain your data.
keywords: ftp;sftp
seo-description: SFTP is a secure protocol for transferring data that ensures that nobody can see your data but you. Adobe Engineering Services can set up an SFTP account to securely retain your data.
seo-title: Secure File Transfer Protocol
solution: Analytics
title: Secure File Transfer Protocol
uuid: 7f0b343d-16a5-4cd3-80ad-97c4e7a6bb77
index: y
internal: n
snippet: y
translate: y
---

# Secure File Transfer Protocol


## Push Delivery {#section_A47831BB1DCA490BB57F0940617AA506}

This means that Adobe's servers "push" the file to your servers. Essentially, we deliver it to your end point. 

[ Data Warehouse ](ftp_sftp_dw.md#concept_904ADB7B4FE04DCCB90EFDB6D0DB1076) and [ Analytics Data Feed ](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) can push data via SFTP. 

The following Analytics tools **cannot** push data via SFTP: 

* Reports &amp;amp; Analytics
* Ad Hoc Analysis
* Report Builder

## Pull Delivery {#section_FA29FAEF02FE40B8B32452146A036F48}

This means that the file is sent to one of Adobe's servers using normal FTP. If you want the file on your server, you have to pull it off Adobe's server using SFTP from your server to Adobe's FTP server. You can do this using one of three methods: 

* [ Connect to Adobe via SFTP without a password. ](ftp_sftp_cert_auth.md#concept_962A381F42A4472AA366A08CCC962846)
* [ Connect to an Adobe FTP Account with SFTP. ](ftp_sftp_connect.md#concept_01176600188441C6AFB28F5E264D89F8)
* You can push any reports you want to Adobe's FTP-like data feeds/R&amp;amp;A/Ad Hoc, and so on and then Pull them off. Adobe cannot deliver these reports to the SFTP server you have set up.
