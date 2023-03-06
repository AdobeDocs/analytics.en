---
description: Set up and use Adobe-hosted FTP accounts.
keywords: ftp;sftp
title: Set up FTP accounts - overview
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
---
# Set up FTP accounts - overview

Set up and use Adobe-hosted FTP accounts.

Adobe maintains highly available, high-performance FTP clusters that are specifically designed to improve file transfer reliability, while continuing to ensure high performance.

Adobe customers receive maintenance notifications through their standard process, as maintenance events are scheduled. To ensure that the Adobe FTP systems function as designed and continue to provide secure and reliable, high performance data transfer, Adobe requests adherence to the following guidelines:

* Most Adobe FTP accounts (classifications, Data Sources, and others) are enabled automatically when the given feature is set up. For Data Feed and general file delivery accounts, Adobe Customer Care can set up a new FTP account for you. This process is in place to ensure both security and space available for the FTP account.
* Users should remove data delivered by Adobe to the FTP account after the data has been successfully transferred to their systems.
* Notify Adobe when FTP accounts are no longer needed so they can be deactivated.

The Adobe FTP host name is `ftp.omniture.com` or `ftp2.omniture.com`.

This information, along with a username and password, should be provided either within the [!UICONTROL Experience Cloud] (for classifications and Data Sources), or by the Adobe representative responsible for setting up the account at your request. If you do not know what FTP address to use, contact your Adobe Account Team, who can provide the correct address. In addition, for classifications and Data Sources accounts, Adobe does not have a specific time of day that FTP files are processed. Instead, Adobe uses a script that constantly polls FTP accounts for new files process. Files uploaded into these accounts are processed as quickly as possible.
