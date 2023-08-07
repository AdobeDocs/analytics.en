---
description: Instructions to set up secure transfer with Adobe FTP servers.
keywords: ftp;sftp
title: Connect to an Adobe FTP account with SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
---
# Connect to an FTP account with SFTP

To set up secure transfer with FTP:

1. (Conditional) If you want to set up secure transfer with Adobe FTP servers:

   1. Request an Adobe hosted FTP account (50 MB quota).

   1. Create Public/Private RSA keys. 
   
      * In Linux environment, run: 

        ```
        ssh-keygen -t rsa
        ```

      * In a Windows environment, use puttyGen.

1. (Conditional) If you want to set up secure transfer with your own FTP location, you must have an SFTP host, username, and the destination site that contain a valid RSA or DSA public key. You can download the appropriate public key when creating the feed.

1. Create a file named [!DNL authorized_keys] (no extension).

1. Copy the contents of the Public key into [!DNL authorized_keys].

1. Upload [!DNL authorized_keys] to an FTP account:

    * Connect to the Adobe FTP account.
    * Create a [!DNL .ssh] directory (if it does not already exist).
    * Upload the [!DNL authorized_keys] file to the [!DNL .ssh] directory.

1. Test the connection by logging in to the FTP account using SFTP.

For more detailed information, see [How to Connect to Adobe via sFTP Without a Password_...](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).
