---
description: Data workbench can be configured to allow only certain users to change certain workspaces.
seo-description: Data workbench can be configured to allow only certain users to change certain workspaces.
seo-title: Configure a locked workspace
solution: Analytics
title: Configure a locked workspace
topic: Data workbench
uuid: 1c3c6681-a7af-480c-9a8d-4860b56d2d18
index: y
internal: n
snippet: y
---

# Configure a locked workspace

Data workbench can be configured to allow only certain users to change certain workspaces.

 While a workspace is locked, users can make selections in most visualizations and sort the data in tables but cannot otherwise change the workspace. This functionality prevents users from making unintentional changes to the workspaces.

The following three elements work together to control the locking of workspaces:

* **A folder.lock or *workspace name*.lock file:** A [!DNL folder.lock] file specifies whether the workspaces in a particular folder are locked, while a workspace [!DNL name.lock] file specifies whether a particular workspace is locked. 

* **The Unlock parameter in a user’s [!DNL Insight.cfg] file:** This parameter specifies whether that user can temporarily unlock locked workspaces. 
* **The Temporarily Unlock menu option:** When the Unlock parameter in the user’s [!DNL Insight.cfg] is set to true, this option appears automatically in the title bar menu of each locked workspace to provide a way for the user to unlock it.

For information about [!DNL folder.lock] and workspace [!DNL name.lock] files, see the following section. For information about setting the Unlock parameter, see [Setting the Unlock Parameter](../../../data-workbench-client/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept_B018A85C6217489AA01B17845872DF7F). For information about the [!UICONTROL Temporarily Unlock menu] option, see [Unlocking a Workspace](../../../data-workbench-client/c-get-started/c-work-worksp/c-unlock-wksp.md#concept_18ADA952AECF45C79A806B31B294023E). 
