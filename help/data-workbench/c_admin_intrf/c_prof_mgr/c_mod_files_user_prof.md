---
description: You can use the Profile Manager to download files that you want to modify.
seo-description: You can use the Profile Manager to download files that you want to modify.
seo-title: Modify local files in the user profile
solution: Analytics
title: Modify local files in the user profile
topic: Data workbench
uuid: 286fa6fe-26c8-4dd8-9b2f-662d66cb30b2
index: y
internal: n
snippet: y
---

# Modify local files in the user profile

You can use the Profile Manager to download files that you want to modify.

 You might want to download a file to overwrite your existing, local file with the original version of the file or open, view, and modify files that cannot be accessed from the workspace menus.

**To download a file**

1. In the [!UICONTROL Profile Manager], open the necessary folders and subfolders to locate the file that you want to download. 
1. Right-click the check mark next to the name of the file and click **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Configuration ( [!DNL .cfg]), dimension ( [!DNL .dim]), and metric ( [!DNL .metric]) files can be edited directly in a profile folder and saved to the server without making them local and separately saving them to the server. Simply right-click the check mark next to the name of the file and click **[!UICONTROL Open]** > **in workstation**.

After the file has been downloaded to the local computer, a check mark appears in the [!UICONTROL User] column, which indicates that a local copy of the file resides in the User\*profile name* folder on your computer. Note that the check mark is the same color as the check mark in the *profile name* column. This indicates that the local file has the same Modified date and time as the file in the *profile name* folder.

**To modify the file**

1. Right-click the check mark next to the file name in the [!UICONTROL User] column. 
1. Click one of the following menu options, depending on how you want to edit the file:

    * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** if you are editing a [!DNL .vw] file or a [!DNL .cfg] file in a workspace. 
    
    * **Open** > **in vw. Editor **if you are editing a .vw file to add new parameters. 
    
    * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** if you are opening a text file or need to add new parameters to a [!DNL .cfg] file. 
    
    * **[!UICONTROL Open]** > **[!UICONTROL folder]** if you want to open the folder in which the file is located on your computer

1. Edit the file as desired, then save the file.

In the [!UICONTROL Profile Manager], note that the check mark in the [!UICONTROL User] column for the file you edited has changed color. This indicates that the local file is now different from the version in the *profile name* folder. If necessary, you can publish the revised version of the file to the profile for use by other users working with this profile. 
