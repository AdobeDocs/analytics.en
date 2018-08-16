---
description: Instructions to set up secure transfer with Adobe FTP servers.
keywords: ftp;sftp
seo-description: Instructions to set up secure transfer with Adobe FTP servers.
seo-title: Connecting to an Adobe FTP Account with SFTP
solution: Analytics
title: Connecting to an Adobe FTP Account with SFTP
uuid: 89f14e7d-0617-47a1-bac1-7296f1a58e91
index: y
internal: n
snippet: y
translate: y
---

# Connecting to an Adobe FTP Account with SFTP


1. Request an Adobe hosted FTP account (50 MB quota).
1. Create Public/Private RSA keys. In Linux, run: 
   ```
   ssh-keygen&amp;nbsp;-t&amp;nbsp;rsa
   ```
   If you are in a Windows environment, use puttyGen to create the keys. 

1. Create a file named [!DNL  authorized_keys] (no extension).
1. Copy the contents of the Public key into [!DNL  authorized_keys].
1. Upload [!DNL  authorized_keys] to an FTP account: 
    * Connect to the Adobe FTP account.
    * Create a [!DNL  .ssh] directory (if it does not already exist).
    * Upload the [!DNL  authorized_keys] file to the [!DNL  .ssh] directory.

1. Test the connection by logging in to the FTP account using SFTP.
For more detailed information, see [ How to Connect to Adobe via sFTP Without a Password_... ](../../ftp_and_sftp_bucket/ftp_sftp/ftp_sftp_cert_auth.md#concept_962A381F42A4472AA366A08CCC962846). 
