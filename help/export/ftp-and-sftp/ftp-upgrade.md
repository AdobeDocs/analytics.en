---
description: Upgrades to Adobe FTP servers can introduce new configurations that affect automation scripts (often used to download or upload data regularly), which are often built to rely on certain server settings.
keywords: ftp;sftp
title: Upgrade Adobe FTP and SFTP servers
feature: FTP Export
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
TQID: 'https://experienceleague.adobe.com/RJHgVwgnmCLRuNTyjKx-D6SlOovFYS0T5-7topZkcVY'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Upgrade Adobe FTP and SFTP servers

Upgrades to Adobe FTP and SFTP servers can introduce new configurations that affect automation scripts (often used to download or upload data regularly), which are often built to rely on certain server settings.

For example, a new success status is introduced, affecting a script that uses the success status to trigger a certain action. Adobe pro-actively notifies users of such configuration changes. If Adobe notifies you that an FTP server upgrade is imminent, check your automation scripts to make sure they are still working correctly.
