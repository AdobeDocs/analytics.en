---
title: SFTP services upgrade - FAQ
description: Frequently asked questions on the planned SFTP services upgrade in May, 2022.
feature: FTP Export
exl-id: e271b545-0769-4a69-9d7f-dc46bc654737
---
# SFTP services upgrade - FAQ

On **May 2, 2022**, Adobe Analytics will upgrade its Secure File Transfer Protocol [SFTP] services in order to provide improved security for file transfers. With this change, some SFTP client configurations will no longer be supported. We will also add some connection options which will available by **March 1, 2022**. This will only impact data sent to or retrieved from Adobe Analytics using SFTP. The FTP protocol will not be impacted. In order to avoid service disruptions, please ensure your SFTP clients (code, tools, services) will be in accordance with the changes detailed below.

## How can I determine which algorithms, connection types, and protocols are currently used by my organization?

The FTP/SFTP software you are using should indicate what specific settings are being used in the connections you have configured for exchanging data with Adobe Analytics. This software should also include documentation about the different options available for connections. The options that will be supported after this update are widely supported and accepted in the industry.

The connection options that will be removed are generally considered obsolete and not used in current software. If you upgraded your FTP/SFTP software within the last three years, you likely already have a compliant connection.

## Which Adobe Analytics features use SFTP for data ingestion?

The following features provide an option to upload data to Adobe Analytics using SFTP.

* [Classifications](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html)

* [Data Feeds](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datafeeds.html)

* [Data Sources](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datasources.html)

* [Data Warehouse delivered reports](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-dw-reports.html)

* Additionally, some custom implementations created through [Engineering Services](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-eng-services.html) may use SFTP to exchange data with Adobe.

## What specific changes will be included in this update? 

Below is a detailed list of which connections and algorithms will be removed and which will be
supported:

* SFTP protocol mac algorithms:

   * We will no longer support: hmac-md5, hmac-md5-96, hmac-ripemd160, hmacripemd160@openssh.com, hmac-sha1, hmac-sha1-96, hmac-sha1-etm@openssh.com, umac-64-etm@openssh.com, umac-64@openssh.com

   * We will only support: hmac-sha2-512-etm@openssh.com, hmac-sha2-256-etm@openssh.com, umac-128-etm@openssh.com, hmac-sha2-512, hmacsha2-256, umac-128@openssh.com

* SFTP protocol ciphers algorithm:

   * We will no longer support: 3des-cbc, aes128-cbc, aes128-gcm@openssh.com, aes192-cbc, aes256-cbc, aes256-gcm@openssh.com, arcfour, arcfour128, arcfour256, blowfish-cbc, cast128-cbc, rijndael-cbc@lysator.liu.se

   * We will only support: aes128-ctr, aes192-ctr, aes256-ctr

* SFTP protocol supported connections:

   * We will no longer support the usage of scp and rsync commands or connections over the sftp protocol

   * We will only support pure SFTP protocol connections

* FTP/SFTP clients/protocols supported:

   * FTP: vsftpd version 3.0.2-25 or higher

   * SFTP: openssh version 7.4p1-21 or higher
