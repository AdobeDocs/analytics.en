---
description: Upgrades to Adobe FTP servers can introduce new configurations that affect automation scripts (often used to download or upload data regularly), which are often built to rely on certain server settings.
keywords: ftp;sftp
title: Upgrade Adobe FTP servers
uuid: cc9e5e13-e213-480f-9ff6-3dbec24baeee
---

# Upgrade Adobe FTP servers

Upgrades to Adobe FTP servers can introduce new configurations that affect automation scripts (often used to download or upload data regularly), which are often built to rely on certain server settings.

For example, a new success status is introduced, affecting a script that uses the success status to trigger a certain action. Adobe pro-actively notifies users of such configuration changes. If Adobe notifies you that an FTP server upgrade is imminent, check your automation scripts to make sure they are still working correctly.
