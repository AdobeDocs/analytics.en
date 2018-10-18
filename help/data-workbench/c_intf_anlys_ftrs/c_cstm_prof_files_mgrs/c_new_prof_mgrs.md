---
description: The Profile Manager displays all of the directories associated with your working profile.
seo-description: The Profile Manager displays all of the directories associated with your working profile.
seo-title: Create a Profile Manager
solution: Analytics
title: Create a Profile Manager
topic: Data workbench
uuid: 4edaad85-1b47-4ca3-a807-d2e2b51c639f
index: y
internal: n
snippet: y
---

# Create a Profile Manager

The Profile Manager displays all of the directories associated with your working profile.

You may want to access a subdirectory of the [!UICONTROL Profile Manager] without having to navigate its entire directory structure. For example, the [!UICONTROL Metrics] and [!UICONTROL Workspaces] menu options available on the [!UICONTROL Manage] menu of the workspace window menu enable you to open the Profile Manager Metrics and Workspaces folders, respectively.

For more information about the [!UICONTROL Profile Manager], see [The Profile Manager](../../c_admin_intrf/c_prof_mgr/c_prof_mgr.md#concept_2C8F60CC84D044BFB57DDF947B1DB263).

By default you have access to the following managers:

* **[!UICONTROL Metrics Manager]:** Displays the contents of the Profile Manager’s Metrics folder. You can open, edit, remove, or copy the metrics defined within each profile. 
* **[!UICONTROL Reports Manager]:** Displays the contents of the Profile Manager’s Reports folder. You can open, edit, remove, or copy report workspaces or [!DNL report.cfg] files. 

* **[!UICONTROL Workspaces Manager]:** Displays the contents of the Profile Manager’s Workspaces folder. All of the files for configuring the [!UICONTROL Worktop]’s tabs are located here. See [Customizing Worktop Tabs](../../c_intf_anlys_ftrs/c_cstm_wktp_tabs/c_cstm_wktp_tabs.md#concept_0F1E6061B03949199326DC6DF71A52BC).

[!DNL Data workbench] enables you to create additional profile managers that display one subdirectory from the [!UICONTROL Profile Manager]. Each manager that you create must have a [!DNL .vw] file that specifies the [!UICONTROL Profile Manager] directory whose contents it shows and the properties of that window. You can use the [!DNL .vw] file for any of the provided managers as a template.

**To create a Profile Manager**

1. In the [!UICONTROL Profile Manager], click the **[!UICONTROL Menu]** directory to view its contents. 
1. Within the Menu directory, click the **[!UICONTROL Admin]** directory and then the **[!UICONTROL Profile]** directory. The [!DNL .vw] files for the existing managers are located here. 
1. In the *profile name* column, right-click the check mark for the one of the [!DNL .vw] files (for example, [!DNL Workspaces.vw]), then click **[!UICONTROL Make Local]**.

   A check mark for the file appears in the [!UICONTROL User] column. 

1. Right-click the check mark for the [!DNL .vw] file in the [!UICONTROL User] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 
1. In the [!UICONTROL Profile Path] field, type the [!UICONTROL Profile Manager] directory for which you want to create a new manager. Be sure to include the slash (/) after the directory name.

   ```
   window = simpleBorderWindow:
   client = scrollWindow: 
   client = fileManager:
     Profile Path = string: directory name/
     size = v3d: (820, 5649, 0)
     scroll_offset = v3d: (0, 0, 0)
     size = v3d: (830, 881, 0)
     pos = v3d: (525, 162, 0)
     size = v3d: (830, 900, 0)
   ```

1. In Notepad, click **[!UICONTROL File]** > **[!UICONTROL Save As]** to save the edited file to the *Data Workbench installation folder*\User\*working profile name*\Menu\Admin\Profile Management.

   Be sure to change the name of the [!DNL .vw] file to reflect the directory in the [!UICONTROL Profile Manager] to which it corresponds. 

1. (Optional) To make the changes available to all users of the working profile, right-click the check mark for the [!DNL .vw] file in the [!UICONTROL User] column and click **[!UICONTROL Save to]** > < **[!UICONTROL working profile name]**>.

