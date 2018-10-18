---
description: The Unlock parameter in a user’s Insight.cfg file specifies whether that user has permission to temporarily unlock locked workspaces for editing.
seo-description: The Unlock parameter in a user’s Insight.cfg file specifies whether that user has permission to temporarily unlock locked workspaces for editing.
seo-title: Set the unlock parameter
solution: Analytics
title: Set the unlock parameter
topic: Data workbench
uuid: 77a9cc4c-ffb1-4bc0-b68e-350fe3145ae8
index: y
internal: n
snippet: y
---

# Set the unlock parameter

The Unlock parameter in a user’s Insight.cfg file specifies whether that user has permission to temporarily unlock locked workspaces for editing.

If the Unlock parameter is already present in the user’s [!DNL Insight.cfg] file, you can edit the parameter using Data Workbench. If it is not already present in the user’s [!DNL Insight.cfg] file, you must add it to the file using a text editor, such as Notepad.

**To set an existing [!UICONTROL Unlock] parameter in the Insight.cfg file**

1. In a workspace, right-click **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. The [!DNL Insight.cfg] file opens. 
1. For the Unlock parameter, type either true or false. True enables the user to temporarily unlock any locked workspace, while false does not. 
1. To save your configuration changes, right-click **[!UICONTROL Insight.cfg (modified)]** at the top of the window and click **[!UICONTROL Save as Insight.cfg]**.

**To add the Unlock parameter to the Insight.cfg file**

1. Navigate to your Data Workbench installation directory and open the [!DNL Insight.cfg] file using a text editor, such as Notepad. 
1. Add the Unlock parameter to the end of the file, as in the following example:

[!DNL Unlock = bool: false] 

1. Set the value to either true or false. True enables the user to temporarily unlock any locked workspace, while false does not. 
1. Save and close the file.

