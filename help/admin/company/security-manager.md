---
description: Enables you to control access to reporting data. Options include strong passwords, password expiration, IP login restrictions, and email domain restrictions.
title: Security Manager
feature: Company Settings
exl-id: 6dcf0354-4b4a-4bd5-ba6c-ae42c7b9e4df
---
# Security Manager

The Security Manager lets you control access to reporting data. Options include strong passwords, password expiration, IP login restrictions, and email domain restrictions.

## Settings

 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Company settings]** > **[!UICONTROL Security]** 

| Setting | Description |
| --- | --- |
| Require Strong Passwords | Forces users to create more secure passwords that adhere to the following rules: <ul><li>Must be at least eight characters in length.</li><li>Must have at least one symbol/number character between the first and last characters.</li><li>Must have at least one alpha character.</li><li>Cannot be found in a dictionary or contain words from a dictionary (English).</li><li>May not include any three (3) consecutive characters from the login username.</li><li>Must be different than the previous 10 passwords.</li></ul>**Note**: This feature is enforced on new passwords going forward. It does not check existing passwords, or force users to change existing passwords. For this reason, consider enabling password expiration to force users to change their passwords and adhere to the strong password rules. |
| Password Expiration | Forces users to regularly change their user account password. You can specify the interval at which you want passwords to expire, and force passwords to expire immediately. |
| Enforce IP Login Restrictions| (This feature is no longer available as of January 2021.)<br> Limits report access to specific IP addresses or IP address ranges. You can add up to 100 entries in the IP Address Filter list, and each entry can be a specific address or a range of addresses. Enforce IP Login Restrictions is not enforced until there is at least one entry in the IP Address Filter list. Accepted IP Address: To specify an IP address range, enclose the range in brackets (for example, `192.168.10.[20-240]`). You can also use wildcards to specify any number from 0 to 255 (for example, `192.168.[10-14].*8`) Failed logins are logged and viewable from the [Usage and Access Log](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html#section_6FBAF92D9EA244809C45A78A2F0A7232). |
| Enforce Email Domain Restrictions | Filters the email addresses and domains where Analytics sends bookmarks, downloadable reports, and alerts. The email filter list supports up to 100 entries, and each entry can be an email address or an entire email domain. If a scheduled report has an unapproved email destination, Analytics sends an email notification of the problem, and a link to unschedule the report. **[!UICONTROL Enforce Email Domain Restrictions]** is not enforced until there is at least one entry in the Accepted Email Domain Filter list. **[!UICONTROL Accepted Email Address and Domains]**: To specify an IP address range, enclose the range in brackets (for example, `192.168.10.[20-240]`). You can also use wildcards to specify any number from 0 to 255 (for example, `192.168.[10-14].*`)|
| Password Recovery Notification | Notifies the specified administrators when a user attempts to reset a user account password. **[!UICONTROL Available Admins]**: Displays all administrators. You can Ctrl+click and Shift+click to select multiple administrators. **[!UICONTROL Email Members]**: Displays the currently defined email group. |
