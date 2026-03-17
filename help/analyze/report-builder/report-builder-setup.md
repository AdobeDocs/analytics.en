---
title: Set Up Report Builder
description: Learn through a complete guide to install and configure Adobe Analytics Report Builder for Excel. Step-by-step setup instructions for seamless integration.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 9d0161a9-ee7b-43a9-92ad-4079cf4b9c6c
---
# Set up Report Builder

This article outlines the requirements to use Report Builder for Adobe Analytics in [!DNL Microsoft] [!DNL Excel]. And how to install and set up the add-in.

## Requirements

Report Builder for Adobe Analytics is supported on the following operating systems and web browsers.

### macOS

- macOS Version 10.x or later
- All [!DNL Microsoft] [!DNL Excel] Versions

### Windows

- Windows 10, version 1904 or later
- [!DNL Excel] Version 2106 or later

  All Windows desktop [!DNL Excel] users must install Microsoft Edge Webview2 to use the add-in. To install the controller:

  1. Go to <https://aka.ms/webview2installer>.
  1. Select and download the Evergreen Standalone Installer.
  1. Follow the installation prompts.

### Web Office

- Supports all browsers and versions


## Report Builder Excel Add-in

You must install the Report Builder [!DNL Excel] Add-in to use [!DNL Report Builder] for Adobe Analytics. Once you install the Report Builder [!DNL Excel] Add-in, you can access Report Builder from within an open [!DNL Excel] workbook.

### Download and install the Report Builder Add-in

To download and install the Report Builder Add-in

1. Launch [!DNL Excel] and open a new workbook.

1. Select **[!UICONTROL Insert]** > **[!UICONTROL Get Add-ins]**.

1. In the Office Add-ins dialog, select the Store tab.

1. Search for "Report Builder" and click **[!UICONTROL Add]**.

1. In the License terms and privacy policy dialog box, click **[!UICONTROL Continue]**.

**If the Store tab isn't displayed**

1. In [!DNL Excel], select File > Account >Manage Settings.

1. Check the box next to "Enable optional connected experiences"

1. Restart [!DNL Excel].

**If your organization blocks access to the Microsoft Store**

- Reach out to your IT or security team to request approval for the Report Builder Add-in. After approval is granted, in the Office Add-ins dialog, select the **[!UICONTROL Admin Managed]** tab. 

   ![The Admin Managed tab in Office Add-ins dialog.](./assets/image1.png)

- Alternatively, you can manually retrieve the [manifest file](https://reportbuilder.an.adobe.com/manifest.xml) and host the file on your own IT infrastructure. <br/>Please follow the Microsoft Office [online documentation](https://learn.microsoft.com/en-us/office/dev/add-ins/publish/publish) for instructions on how to install an Excel Manifest file not served from the Microsoft Store.

After installing the Report Builder Add-in, the Report Builder icon is displayed in the [!DNL Excel] ribbon under the Home tab.

![The Report Builder icon in Excel](/help/analyze/report-builder/assets/rb_app_icon.png)

## Log in to Report Builder

After you have installed the Report Builder for Excel Add-in for your operating platform or browser, follow these steps to log in to Report Builder.

1. Open an Excel workbook.

1. Click the Report Builder icon to launch Report Builder.

1. From the Adobe Report Builder toolbar, click **[!UICONTROL Login]**.

    ![Click the Report Builder login button.](/help/analyze/report-builder/assets/rb_login.png)

1. Enter your Adobe Experience ID account information. Your account information should match your Adobe Analytics credentials.

    ![Your login icon and organization.](/help/analyze/report-builder/assets/image4.png)

After you log in, your login icon and organization appears at the top of the panel

## Switch organizations

When you first log in, you are logged in to the default organization assigned to your profile.

1. Click the name of the organization that is displayed when you log in.

1. Select an organization from the list of available organizations. Only organizations that you have access to are listed.

    ![The list of organizations that you can access.](/help/analyze/report-builder/assets/image5.png)

## Sign out

You can sign out from Report Builder from the user profile.

1. Save changes to any open workbooks.

1. Click the avatar icon to display your user profile.

    ![Your user profile avatar and the Sign Out button.](/help/analyze/report-builder/assets/image6.png)

1. Click **Sign Out**.
