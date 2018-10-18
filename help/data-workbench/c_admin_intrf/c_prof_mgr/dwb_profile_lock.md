---
description: The Internal.cfg file applied in the Profile Manager prevents changes by users to your custom profiles by the Profile, Dimensions, Reports, Workspaces, Metrics, and Filters managers.
seo-description: The Internal.cfg file applied in the Profile Manager prevents changes by users to your custom profiles by the Profile, Dimensions, Reports, Workspaces, Metrics, and Filters managers.
seo-title: Lock a profile in the Workstation
title: Lock a profile in the Workstation
uuid: e96f85a6-2371-47d5-8050-38e378fe12be
index: y
internal: n
snippet: y
---

# Lock a profile in the Workstation

The Internal.cfg file applied in the Profile Manager prevents changes by users to your custom profiles by the Profile, Dimensions, Reports, Workspaces, Metrics, and Filters managers.

You can prevent profile files from being modified and overwritten when using the managers by saving the **[!DNL Internal.cfg]** file to your custom profile in the Profile Manager. This configuration file prevents users from overwriting multiple files when working in the managers (accessed from the **Admin** > **Profile** menu).

**Lock a profile in the Profile Manager**

1. In the workspace, right-click **Admin** > **Profile Manager**. 
1. In the **Profile Manager**, right-click **[!DNL Context > Internal.cfg]** and **Make Local**. 
1. Right-click checkmark in **User** column and save to a <*custom profile*>.

   ![](assets/dwb_lock_profiles.png)

**Note**: Only changes to profile files by the managers are prevented when saving the **[!DNL Internal.cfg]** to a custom profile in the Profile Manager. You can still save workspaces to the server from the worktop using the **Save to server** command. 
