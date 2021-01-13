---
description: Information about the three ways to sign in to Report Builder.
title: Report Builder Sign-In
topic: Report builder
uuid: 9a21b791-e323-46d2-b850-2d67babe964b
---

# Report Builder Sign-In

>[!IMPORTANT]
>
>Report Builder version 5.6.47 and later supports Experience Cloud login only and does not support legacy logins such as Site Catalyst Single Sign-on or the Standard Login. By April 30, 2021, all Report Builder users must update the Report Builder Add-in to version 5.6.47 or later which includes a critical update to the log-in process.

To log in to Report Builder, use your Experience Cloud login account.

## Experience Cloud {#section_1FA230F35AB54021A874A7A28DE4C850}

The Experience Cloud login lets you use your Enterprise ID (email and password) to log in to the Adobe Experience Cloud. Click **[!UICONTROL Sign In]** > **[!UICONTROL Sign in with an Enterprise ID]** to be redirected to your company's single sign-on page. For more information on Enterprise ID, click [here](https://helpx.adobe.com/enterprise/kb/enterprise-id-faq.html#whatis).

![](assets/adobe_id_login.png)

>[!NOTE]
>
>The Experience Cloud login is session based and the token expires after 30 days.

## Sign in to Report Builder

To log in to Report Builder

1. In Excel, click **[!UICONTROL Add-Ins]**.
1. Click **[!UICONTROL Sign In]**. Other actions that sign you in include:

    * Click **[!UICONTROL Create]**.
    * [Select a request in the Request Manager](/help/analyze/report-builder/manage-requests/r-arb-manage-requests.md), then click **[!UICONTROL Add]** or **[!UICONTROL Manage]**.
    * Double-click a request in Excel.

1. Complete the fields on the [!UICONTROL Login] page, then click **[!UICONTROL OK]**.

## Legacy login types

>[!IMPORTANT]
>
>By April 30, 2021, legacy login types will not work. All Report Builder users must update the Report Builder Add-in to version 5.6.47 or later which includes a critical update to the log-in process. **Report Builder version 5.6.47 and later supports Experience Cloud login only and does not support legacy logins such as the Standard Login or the Site Catalyst Single Sign-on.**

<!-- ![](assets/login_screen.png) -->

* [Standard](/help/analyze/report-builder/setup/login.md#section_6D54B8ADAE7F416BB83F5082B3771CFA)
* [Site Catalyst Single Sign-On](/help/analyze/report-builder/setup/login.md#section_6970A5F926774976B85FFE576610E85F)

## Standard {#section_6D54B8ADAE7F416BB83F5082B3771CFA}

Use this login if you want to sign in to Report Builder using your Adobe Analytics credentials.

**Report Builder login - field definitions**

| Field | Definition |
|--- |--- |
|Company|The Company login credential that you use for Adobe Analytics.|
|Username|The Username login that you use for Adobe Analytics. Scheduled tasks for a user are linked to the username. You can view your scheduled tasks from any computer if you log in to report builder with the same login credentials.|
|Password|Your Analytics password.|
|Remember me|Login information is encrypted and stored in a user profile file on the machine where Report Builder is installed. Because login information is saved, anyone using the same PC as the report creator who opens a spreadsheet containing a report can refresh and edit the data. If you share your computer with others and you wish to keep the spreadsheet data private, do not enable this option.  To disable your automatic login setting, click **[!UICONTROL Log in With Different Credentials]** on the Toolbar and disable **[!UICONTROL Remember Me]**.|
|Use a Proxy Server|Enable if you are accessing the Internet through a proxy server and are required to provide a proxy username and password.|

## Single sign-on {#section_6970A5F926774976B85FFE576610E85F}

This (legacy) single sign-on logs you in to Adobe Analytics only, not the entire Experience Cloud.

You can also type in a domain and the system will recognize the domain and redirect you to your company's sign-in page to log in to Adobe Analytics.
