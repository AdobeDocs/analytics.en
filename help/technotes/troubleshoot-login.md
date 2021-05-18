---
title: Troubleshoot logging in to Adobe Analytics
description: Steps to take when you cannot log in to Adobe Analytics.
exl-id: e670a043-c55b-4717-9b60-613ea4d04382
---
# Troubleshoot logging in to Adobe Analytics

Adobe Analytics uses multiple authentication methods to log in:

* Adobe ID through the Experience Cloud
* Legacy Analytics ID
* Single sign-on

**If you regularly access Analytics and randomly start encountering login issues, clearing your browser's cookies and cache resolves most issues.**

Occasionally, availability issues can impact the ability to log in. Check [status.adobe.com](https://status.adobe.com) for any open incidents. Otherwise, use the appropriate section depending on your organization's authentication method.

## Adobe ID

Troubleshoot issues with logging in to Adobe Analytics using the Experience Cloud.

1. Navigate to [experience.adobe.com](https://experience.adobe.com). If you are unable to access this site, your organization might not allow this domain through your firewall. Work with your organization's IT team to allow it. See [IPs and domains used in the Adobe Experience Cloud](https://helpx.adobe.com/analytics/kb/adobe-ip-addresses.html) for helpful information to give to your IT team.

2. Authenticate using Adobe ID: Click **[!UICONTROL Sign In with an Adobe ID]**. If you are unable to sign in, double check that your email address is typed correctly. Otherwise, click **[!UICONTROL Reset password]** and follow the prompts to reset your Adobe ID password.

3. Access Analytics after authenticating: Click the 9-grid icon in the top right, then click Analytics. If you do not have this option or it is greyed out, work with a product admin within your organization to make sure that you have the correct permissions to access Analytics.

## Legacy Analytics ID

A user in your organization can receive the following error when they attempt to log in:

*As a security precaution, this account has been locked due to too many failed attempts to log in.*

If clearing the browser's cookies/cache does not resolve the issue, work with an Analytics administrator in your organization to reset the user's password.

>[!IMPORTANT]
>
>The following steps to reset a user's password only applies to legacy Analytics ID's, not Adobe ID's. If your organization uses Adobe ID's, you can manage user accounts at [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Log in to Adobe Analytics with an account that has administrative rights.
2. Navigate to **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]**.
3. Click the **[!UICONTROL Users]** tab then click **[!UICONTROL Edit]** next to the desired user.
4. Change the password to any value, and check the box **[!UICONTROL Require user to change password on next login]**.
5. Inform the user of the new password.

## Single sign-on

Contact an administrator in your organization to resolve single sign-on issues.

## Expired logins

A user in your organization can receive the following error when they attempt to log in:

*Error: This login has expired.*

This error works as intended. Adobe Analytics provides administrators with the capability to set a date range that a user account is valid. If the current date resides outside the valid date range for the account, they are unable to log in. Work with an Analytics administrator in your organization to extend the valid date range of the login. Adobe Customer Care is not authorized to change valid login date ranges for user accounts.

## Other login issues

If none of the above steps work, determine the breadth of the login issue:

* Does the issue occur when using a different browser, or is it across all browsers?
* Does the issue occur on a different machine on the network, or is it across multiple machines?
* Try logging in using a different network, such as a mobile data connection, library, or home network. Is the issue present across networks?

If the issue is isolated within your network, work with your organization's IT team to resolve it. If it is not limited to a single network, contact Adobe Customer Care.
