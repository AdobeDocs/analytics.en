---
description: Instructions to set up secure transfer with Adobe FTP servers.
keywords: ftp;sftp
title: Connect to an Adobe FTP account with SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
---
# Connect to an Adobe FTP account with SFTP

Instructions to set up secure transfer with Adobe FTP servers.

1. Request an Adobe hosted FTP account (50 MB quota).
1. Create Public/Private RSA keys. In Linux, run: 

   ```
   ssh-keygen -t rsa
   ```

   If you are in a Windows environment, use puttyGen to create the keys.

1. Create a file named [!DNL authorized_keys] (no extension).
1. Copy the contents of the Public key into [!DNL authorized_keys].
1. Upload [!DNL authorized_keys] to an FTP account:

    * Connect to the Adobe FTP account.
    * Create a [!DNL .ssh] directory (if it does not already exist).
    * Upload the [!DNL authorized_keys] file to the [!DNL .ssh] directory.

1. Test the connection by logging in to the FTP account using SFTP.

For more detailed information, see [How to Connect to Adobe via sFTP Without a Password_...](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).
