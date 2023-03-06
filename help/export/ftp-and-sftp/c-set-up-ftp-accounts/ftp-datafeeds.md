---
description: Data Feeds are an export of the clickstream data received by Adobe that offers both standard and custom Data Feeds.
keywords: ftp;sftp
title: Data Feeds
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
---
# Data Feeds

>[!NOTE]
>
>FTP and SFTP are no longer recommended destinations for data feeds. Instead, we recommend using Amazon S3, Google Cloud Platform, Azure RBAC, or Azure SAS as data feed destinations.

Data Feeds are an export of the clickstream data received by Adobe that offers both standard and custom [Data Feeds](/help/export/analytics-data-feed/data-feed-overview.md).

If you have purchased Adobe Data Warehouse, [!UICONTROL Standard Data Feeds] you can set up your own Analytics data feeds. They can be sent to any FTP account (either one set up by Adobe or an external FTP). Adobe Engineering Services offers custom [!UICONTROL Data Feeds] that can be sent by virtually any means.

[!UICONTROL Data Feed]FTP accounts allow 10GB (by default). All other standard FTP accounts are 50MB by default. In cases where clients are using the FTP account for its proper intended use, some users with high traffic amounts can quickly fill up these accounts. When an FTP account is full, no additional files can be pushed to them. Therefore, any files being delivered to that FTP account ( [!UICONTROL Data Feeds], data warehouse requests, and so forth) are not delivered. This is one reason it is important to manage your Adobe FTP account by removing files that have been received and downloaded.

When an FTP account is full, you should download and remove the current files, and let Adobe know the space has been cleared. Adobe can then resend files that have not been delivered. Some tools, such as data warehouse, lets users resend these files. Resending may not require Adobe involvement. If your FTP account appears to be filling up frequently, contact Adobe Customer Care, which can suggest delivery alternatives that can include increasing the FTP space and file number quota on the account.
