---
description: Complete these tasks to employ the Localized Input Method Editor (IME).
seo-description: Complete these tasks to employ the Localized Input Method Editor (IME).
seo-title: Set up the input method editor
solution: Analytics
title: Set up the input method editor
topic: Data workbench
uuid: 1d53e7a3-48f5-47e3-92bb-e4c71ff0d049
index: y
internal: n
snippet: y
---

# Set up the input method editor

Complete these tasks to employ the Localized Input Method Editor (IME).

## 1. Update the server. {#section_5D07A081BEFC4EAA8FDF7FEA904E0D48}

The administrator must first complete these tasks to update the server components:

1. Upgrade to server 6.x. 
1. Create an " [!DNL Insight.zbin]" file. 
1. Place the [!DNL Insight.zbin] file in the root directory of the Report Server where the [!DNL Insight.exe] is located. Then restart the Report Server.

* If the [!DNL .zbin] file is updated from the server, then you will need to exit and re-launch the client for the new [!DNL .zbin] file to take effect. 

* Restart the Report Server service in addition to the client application for the new [!DNL .zbin] file to take effect after updating. 
* The base\localization\&#42;.zbin will be synched from the server. It will be your responsibility as the Data Workbench administrator to select and copy a .zbin files and rename it to "insight.zbin". Then place it in the root directory for the client and Report Server.

**Localized Splash Screens**

Data workbench looks for the following splash screen files:

* English (default): [!DNL Base/Images/<version_product> Splash.png] 
* Chinese (when started with -zh-cn): [!DNL Base/Images/<version_product> Splash zh-cn.png].

If a splash screen is requested but missing, Data Workbench will access the English splash screen by default.

**Server implementation notes**

* An [!DNL Insight.zbin] file is included in the installation folder that contains the [!DNL insight.exe] file. If you connect to servers that don't support localization, Data Workbench will check first for an updated [!DNL zbin] file in the [!DNL Base/Localization] folder. This folder is automatically updated by the server to add or remove [!DNL .zbin] files in this folder. 

* If you connect to a server that doesn't support IME localization, the [!DNL .zbin] files will be removed from the [!DNL Base/Localization] folder and Data Workbench will employ the [!DNL insight.zbin] file in the installation folder. The backup [!DNL insight.zbin] file can be provided in any supported language. 

* For example, you can access an English dictionary at start-up (by providing no command-line argument), but Data Workbench may access the backup [!DNL insight.zbin] if the server does not support localization. In most cases, a Chinese user will start with [!DNL Insight.exe -zh-cn], but may access a backup [!DNL insight.zbin] if needed that is also in Chinese.

## 2. Update the client. {#section_9653D3FCAF2A4337A97B685857E7AEAC}

After updating the server, follow these steps to update each client.

1. To make sure the client does not get updated from the Data Workbench server during this upgrade, set your [!DNL Insight.cfg] argument to false.

   ```
   Update Software = bool: false
   ```

1. Restart the client. 
1. Navigate to the Software and Docs profile (SoftDocs profile) and download the required **[!UICONTROL insight.zbin]** file from the client package: Software\Insight Client\Insight_6.1.zip. 
1. Move the [!DNL insight.zbin] file to where [!DNL insight.exe] is located. 
1. To make sure that the client now gets updated from the server, change the [!DNL Insight.cfg] file argument to true:

   ```
   Update Software = bool: true
   ```

   If this line is missing, then the value will default to [!DNL false] and no IME will be available.

   >[!NOTE]
   >
   >Your client will synchronize with the server and you will see a message stating that your client is updating. At the conclusion of the download, you will get a message asking if your want to restart your client.

1. Click **OK** to restart the client.

   If you get the following message, then it means the [!DNL zbin] file was not placed in the same location as the [!DNL Insight.exe]. 

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

