---
description: Enables you to control access to reporting data. Options include strong passwords, password expiration, IP login restrictions, and email domain restrictions.
solution: Analytics
title: Security Manager
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
---

# Security Manager

The Security Manager lets you control access to reporting data. Options include strong passwords, password expiration, IP login restrictions, and email domain restrictions.

## Settings

 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Company Settings]** > **[!UICONTROL Security]** 

<table id="table_F1AD9DE5094A4FC2B9DA8D01198F944B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Require Strong Passwords </span> </td> 
   <td colname="col2">Forces users to create more secure passwords that adhere to the following rules: 
    <ul id="ul_100CC57EB4374DAA87B2074BA8B46F26"> 
     <li id="li_4D9102C361044FADBC14402A8398F2F3">Must be at least eight characters in length. </li> 
     <li id="li_AFE9568C14894E93BFDFDC84DCD2838D">Has at least one symbol/number character between the first and last characters. </li> 
     <li id="li_ECA05BEF7BFD4430B09D4A953B41D2A6">Has at least one alpha character. </li> 
     <li id="li_6928045588E94E28851BB15991C8D51E">Cannot be found in a dictionary or contain words from a dictionary (English). </li> 
     <li id="li_C3DD4608CA6F43E4B1E4FCFC6D116371">May not include any three (3) consecutive characters from the login username. </li> 
     <li id="li_687838CA01B94EE29EF4C09F485C5537">Must be different than the previous 10 passwords. </li> 
    </ul> <p>Note:  This feature is enforced on new passwords going forward. It does not check existing passwords, or force users to change existing passwords. For this reason, consider enabling password expiration to force users to change their passwords and adhere to the strong password rules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Password Expiration</span> </td> 
   <td colname="col2"> Forces users to regularly change their user account password. You can specify the interval at which you want passwords to expire, and force passwords to expire immediately. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Enforce IP Login Restrictions</span> </td> 
   <td colname="col2"> <p>(This functionality cannot be used in conjunction with Experience Cloud login. Note that this functionality will no longer be available as of October, 2020. [More...](/help/admin/company/login-restrictions-eol.md)) Limits report access to specific IP addresses or IP address ranges. </p> <p>You can add up to 100 entries in the IP Address Filter list, and each entry can be a specific address or a range of addresses. </p> <p> <span class="wintitle"> Enforce IP Login Restrictions</span> is not enforced until there is at least one entry in the IP Address Filter list. </p> <p> <span class="uicontrol"> Accepted IP Address</span>: To specify an IP address range, enclose the range in brackets (for example, 
     <code>
       192.168.10.[20-240]
     </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> <p>Failed logins are logged and viewable from the <a href="/help/admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232"> Usage and Access Log</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Enforce Email Domain Restrictions</span> </td> 
   <td colname="col2"> <p>Filters the email addresses and domains where Analytics sends bookmarks, downloadable reports, and alerts. </p> <p>The email filter list supports up to 100 entries, and each entry can be an email address or an entire email domain. </p> <p>If a scheduled report has an unapproved email destination, Analytics sends an email notification of the problem, and a link to unschedule the report. </p> <p> <span class="wintitle"> Enforce Email Domain Restrictions</span> is not enforced until there is at least one entry in the <span class="wintitle"> Accepted Email Domain Filter</span> list. </p> <p> <span class="uicontrol"> Accepted Email Address and Domains</span>: To specify an IP address range, enclose the range in brackets (for example, 
     <code>
       192.168.10.[20-240]
     </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Password Recovery Notification</span> </td> 
   <td colname="col2"> <p>Notifies the specified administrators when a user attempts to reset a user account password. </p> <p> <span class="uicontrol"> Available Admins</span>: Displays all administrators. You can Ctrl+click and Shift+click to select multiple administrators. </p> <p> <span class="uicontrol"> Email Members</span>: Displays the currently defined email group. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Element | Description |
|--- |--- |
|Require Strong Passwords|Forces users to create more secure passwords that adhere to the following rules: <ul><li>Must be at least eight characters in length.</li><li>Must have at least one symbol/number character between the first and last characters.</li><li>Must have at least one alpha character.</li><li>Cannot be found in a dictionary or contain words from a dictionary (English).</li><li>May not include any three (3) consecutive characters from the login username.</li><li>Must be different than the previous 10 passwords.</li></ul>**Note**: This feature is enforced on new passwords going forward. It does not check existing passwords, or force users to change existing passwords. For this reason, consider enabling password expiration to force users to change their passwords and adhere to the strong password rules.|
|Password Expiration|Forces users to regularly change their user account password. You can specify the interval at which you want passwords to expire, and force passwords to expire immediately.|
|Enforce IP Login Restrictions|(This functionality cannot be used in conjunction with Experience Cloud login. Note that this functionality will no longer be available as of October, 2020. [More...](/help/admin/company/login-restrictions-eol.md))<br> Limits report access to specific IP addresses or IP address ranges. You can add up to 100 entries in the IP Address Filter list, and each entry can be a specific address or a range of addresses. Enforce IP Login Restrictions is not enforced until there is at least one entry in the IP Address Filter list. Accepted IP Address: To specify an IP address range, enclose the range in brackets (for example, `192.168.10.[20-240]`). You can also use wildcards to specify any number from 0 to 255 (for example, `192.168.[10-14].*8) Failed logins are logged and viewable from the [Usage and Access Log](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/logs.html#section_6FBAF92D9EA244809C45A78A2F0A7232).|
|Enforce Email Domain Restrictions|Filters the email addresses and domains where Analytics sends bookmarks, downloadable reports, and alerts. The email filter list supports up to 100 entries, and each entry can be an email address or an entire email domain. If a scheduled report has an unapproved email destination, Analytics sends an email notification of the problem, and a link to unschedule the report. **[!UICONTROL Enforce Email Domain Restrictions]** is not enforced until there is at least one entry in the Accepted Email Domain Filter list. **[!UICONTROL Accepted Email Address and Domains]**: To specify an IP address range, enclose the range in brackets (for example, 192.168.10.[20-240]). You can also use wildcards to specify any number from 0 to 255 (for example, 192.168.[10-14].*)|
|Password Recovery Notification|Notifies the specified administrators when a user attempts to reset a user account password. **[!UICONTROL Available Admins]**: Displays all administrators. You can Ctrl+click and Shift+click to select multiple administrators. **[!UICONTROL Email Members]**: Displays the currently defined email group.|
