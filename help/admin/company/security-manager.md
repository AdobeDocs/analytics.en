---
description: Enables you to control access to reporting data. Options include strong passwords, password expiration, IP login restrictions, and email domain restrictions.
solution: Analytics
title: Security Manager
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
---

# Security Manager

Enables you to control access to reporting data. Options include strong passwords, password expiration, IP login restrictions, and email domain restrictions.

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
   <td colname="col2"> <p>(This functionality cannot be used in conjunction with Experience Cloud login. Note that this functionality will no longer be available as of October, 2020.) Limits report access to specific IP addresses or IP address ranges. </p> <p>You can add up to 100 entries in the IP Address Filter list, and each entry can be a specific address or a range of addresses. </p> <p> <span class="wintitle"> Enforce IP Login Restrictions</span> is not enforced until there is at least one entry in the IP Address Filter list. </p> <p> <span class="uicontrol"> Accepted IP Address</span>: To specify an IP address range, enclose the range in brackets (for example, 
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

## End-of-life for [!UICONTROL Enforce IP login restrictions]

The **[!UICONTROL Enforce IP login restrictions]** feature is a soon-to-be-legacy Analytics feature that allows you to whitelist specific IP addresses that are deemed secure, to allow successful logins and access to your Adobe Analytics environment. In many instances, this feature is used to set up a corporate IP address as the only secure IP address that users can log in from. Therefore, in order to use Adobe Analytics, this requires users to either be at a corporate office or to log in the network via VPN. 

### Why are we considering it for end-of-life?

This feature is broken in some circumstances by the Experience Cloud login migration and/or the Experience Cloud login. It is known to break for customers using **[!UICONTROL Customer Attributes]** or **[!UICONTROL Audience Library]**. 

Additionally, if you own multiple Experience Cloud Solutions, you can circumnavigate this requirement by logging in to the Experience Cloud with one of the other solutions, as this feature does not exist or is not supported outside of Analytics itself. Users could also get around this via IP spoofing.

Finally, Adobe has a functioning and far superior alternative solution via Single-Sign-On and Federated IDs. This feature gives you greater control and security over your users’ login experience.

### How does removal of this feature impact you?

For any customer who has **[!UICONTROL Enforce IP login restrictions]** set up, this feature will be removed in October, 2020. At that time, any IP login restrictions still in place will no longer be enforced. If you still need to restrict login by IP address, you should review and implement the recommended solution of Single-Sign-On and Federated IDs (more info and resources below). 

Additionally, the **[!UICONTROL Enforce IP login restrictions]** manager will be removed from the **[!UICONTROLAdmin > Company Settings > Security Manager]** in the Analytics UI (as shown below). 

![](assets/sec-manager2.png)

### What are your other options?

As stated above, this Analytics feature will be end-of-lifed. To give you time to implement SSO and Federated IDs, we have delayed the EOL date to October 2020. 

Both SSO and Federated IDs are superior solutions to the IP Login Restriction feature we have in place today and will provide you with more control, security and features.

For information on how to set up SSO/Federated IDs, we have the following help documentation available. We recommend that you read them thoroughly and work with your IT department to get them implemented:

* [Single Sign-On and the Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Admin Console - Identity Setup documentation](https://helpx.adobe.com/enterprise/using/set-up-identity.html)
* [Admin Console - Identity Setup tutorial (video)](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Configure Federated ID tutorial (video)](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Single Sign-On - common questions](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [Adobe-supported identity types](https://helpx.adobe.com/enterprise/using/identity.html)

If you want to continue to voice your support for IP Login Restrictions and request that it be provided by the Experience Cloud, you may vote for this feature on our [Forum page](https://forums.adobe.com/ideas/11648). For additional questions or information on SSO/Federated IDs and the EXC, please reach out to Ryan Monger (monger@adobe.com). 
