---
description: Learn about the different save options, including autosave, save as, save as template, and open previous versions.
title: Save projects
feature: Workspace Basics
role: User, Admin
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
---
# Save projects

To save your changes to a project, go to the Workspace **[!UICONTROL Project]** menu. Workspace also auto-saves projects in certain cases. 

## Save project options {#Save} 

There are different save actions you can take under the **[!UICONTROL Project]** menu, depending on how you want to access your analysis in the future. 

| Action | Description | 
|---|---| 
| **[!UICONTROL Save]** | Save changes to your project. If the project is shared, recipients of the project will also see the changes. When you first save your project, you are prompted to give the project a name, (optional) description and add (optional) tags. | 
| **[!UICONTROL Save with notes]** | Before your project saves, add notes about what changed in the project. Notes are stored with the project version and are available to all editors under [!UICONTROL Project] > [!UICONTROL Open previous version]. | 
| **[!UICONTROL Save as]** | Create a duplicate of your project. The original project will not be affected. | 
| **[!UICONTROL Save as template]** | Save your project as a [custom template](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) that becomes available to your organization under **[!UICONTROL Project > New]** | 

![](assets/save-project.png)

## Auto-save {#Autosave} 

Existing projects, i.e. projects that have been saved at least once before, are auto-saved every two minutes to your local machine. New projects that have never been saved are not currently auto-saved.  

There are a few scenarios that may lead you away from unsaved changes to a project, resulting in different available actions.  

### Open another Workspace project 

Adobe provides the option to save before leaving the page. After leaving an existing project, the auto-saved local copy is deleted.

![](assets/existing-save.png)

### Navigate away or close a tab 

The browser warns that unsaved changes will be lost. You can choose to leave or cancel. 

![](assets/browser-image.png)

### Browser crashes or session times out 

For **existing** projects, upon returning to Workspace, you will see a **Project recovery** modal. Selecting “Yes” restores the project from the auto-saved local copy. “No” deletes the auto-saved local copy and opens the last user-saved version of the project. 

![](assets/project-recovery.png)

For **new** projects that have never been saved, unsaved changes are not recoverable.

## Open previous version {#previous-version}

>[!NOTE]
>
>Previous project versions are currently in limited release.

To open a previous version of a project:

1. Go to **[!UICONTROL Project]** > **[!UICONTROL Open previous version]**

   ![](assets/previous-versions.png)
   
1. Review the list of prior versions available. 
   [!UICONTROL Timestamp] and [!UICONTROL Editor] are shown, in addition to [!UICONTROL Notes] if they were added when the [!UICONTROL Editor] saved. Versions without notes are stored for 90 days; versions with notes are stored for 1 year.
1. Select a previous version and click **[!UICONTROL Load]**.
   The previous version then loads with a notification. The previous version does not become the current saved version of your project until you click **[!UICONTROL Save]**. If you navigate away from the loaded version, when you return, you will see the last saved version of the project. 
