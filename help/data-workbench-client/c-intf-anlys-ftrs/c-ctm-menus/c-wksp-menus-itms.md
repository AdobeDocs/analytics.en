---
description: These steps apply only to creating submenus and menu items for the Workspace Window menu.
seo-description: These steps apply only to creating submenus and menu items for the Workspace Window menu.
seo-title: Create a workspace menu and menu item
solution: Analytics
title: Create a workspace menu and menu item
topic: Data workbench
uuid: 696eba3d-2dbf-49e4-9e6e-34ca3a7b6c71
index: y
internal: n
snippet: y
---

# Create a workspace menu and menu item

These steps apply only to creating submenus and menu items for the Workspace Window menu.

You can customize the metric and dimension menus by creating new folders and new derived metrics and dimensions. For more information, see [Creating and Editing Derived Metrics](../../../data-workbench-client/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept_E41723B342A849309874B26232224A40) and [Creating and Editing Derived Dimensions](../../../data-workbench-client/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept_ECE3C3EA8CDF4FC796680173993BFF93).

**To create a new workspace window menu**

1. In the [!UICONTROL Profile Manager], click the **[!UICONTROL Menu]** directory to view its contents. 
1. In the [!UICONTROL User] column for the Menu directory, click **[!UICONTROL Create]** > **[!UICONTROL Folder]**. A folder named New Folder appears in the [!UICONTROL File] column for [!UICONTROL Menu].

   >[!NOTE]
   >
   >You also can create a new folder for any subdirectory within the Menu directory.

1. Rename the new folder by right-clicking in the [!UICONTROL User] column for the folder and typing the new name in the Dir parameter. 
1. Add the desired files to the new folder. 
1. (Optional) In the [!UICONTROL User] column for the new folder, click **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   An [!DNL order.txt] file appears in the [!UICONTROL File] column for the new folder, and a check mark for the new file appears in the [!UICONTROL User] column. 

1. (Optional) Edit the [!DNL order.txt] file as needed. See [Customizing Menus Using Order.txt Files](../../../data-workbench-client/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task_A391800A8DD444DEB3E1516D5189F999). 
1. (Optional) To make the changes available to all users of the working profile, right-click the white check mark for the folder in the [!UICONTROL User] column and click **[!UICONTROL Save Directory to]** > *< **[!UICONTROL working profile name]**>*.

**To add a new menu item to an existing menu**

1. Complete one of the following steps:

    * Create a new item (visualization, annotation, and so on) to add to a menu:

        1. Open a workspace in Data Workbench and create the desired item. 
        1. Save the item to the following directory:

           *Data workbench installation directory*\User\*working profile name*\Work 
        
        1. In the [!UICONTROL Profile Manager], click the **[!UICONTROL Work]** directory to view its contents. 
        1. In the [!UICONTROL User] column, right-click the check mark for the desired file and click **[!UICONTROL Copy]**. 
        1. In the [!UICONTROL User] column for the desired folder, click **[!UICONTROL Paste]**.

           A copy of the file appears in the [!UICONTROL File] column for the new folder, and a check mark for the new file appears in the [!UICONTROL User] column.

    * Copy and paste an existing item from one menu (folder) to another:

        1. In the [!UICONTROL Profile Manager], click the **[!UICONTROL Menu]** directory to view its contents. 
        1. In the *working profile name* column, right-click the check mark for the desired file and click **[!UICONTROL Make Local]**. 
        1. Right-click the check mark for the file in the [!UICONTROL User] column and click **[!UICONTROL Copy]**. 
        1. In the [!UICONTROL User] column for the desired folder, click **[!UICONTROL Paste]**. A copy of the file appears in the [!UICONTROL File] column for the new folder, and a check mark for the new file appears in the [!UICONTROL User] column.

1. (Optional) Edit the [!DNL order.txt] file as needed. See [Customizing Menus Using Order.txt Files](../../../data-workbench-client/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task_A391800A8DD444DEB3E1516D5189F999). 
1. (Optional) To make the changes available to all users of the working profile, right-click the white check mark for each file in the [!UICONTROL User] column and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*. 
1. (Optional) To avoid having a menu item appear in multiple menus, you should delete the corresponding file from its original folder by right-clicking the check mark for the file in the *working profile name* column and clicking **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Repeat this step for the file’s check mark in the [!UICONTROL User] column.

