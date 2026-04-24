---
description: Instructions to set up secure transfer with Adobe FTP servers.
keywords: ftp;sftp
title: Connect to an Adobe FTP account with SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
TQID: https://experienceleague.adobe.com/uXtJtDP58tSIzb9AvoAknAYoMt7SknJSgxRKNgIAXM8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Connect to an FTP account with SFTP

To set up secure transfer with FTP:

1. (Conditional) If you want to set up secure transfer with Adobe FTP servers:

   1. Request an Adobe-hosted FTP account (50 MB quota).

   1. Create Public/Private keys. 
   
      * In Linux environment, run: 

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        If your policy does not allow you to use ed25519, run:

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

        **Note:** This typically applies to customers who operate under FIPS 186-4, as ed25519 is first supported in the newer FIPS 186-5.

      * In a Windows environment, use puttyGen.

1. (Conditional) If you want to set up secure transfer with your own FTP location, you must have an SFTP host, username, and the destination site that contain a valid RSA or ed25519 public key. You can download the appropriate public key when creating the feed.

1. Create a file named [!DNL `authorized_keys`] (no extension).

1. Copy the contents of the Public key into [!DNL `authorized_keys`].

1. Upload [!DNL `authorized_keys`] to an FTP account:

    * Connect to the Adobe FTP account.
    * Create a [!DNL .ssh] directory (if it does not already exist).
    * Upload the [!DNL `authorized_keys`] file to the [!DNL .ssh] directory.

1. Test the connection by logging in to the FTP account using SFTP.

For more detailed information, see [Connect to Adobe via SFTP without a password](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).

