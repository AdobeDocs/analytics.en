---
description: Learn how to work with projects in Analysis Workspace. Use the projects manager to manage (create, delete, move, share, approve, pin, copy, and tag) projects.
keywords: Analysis Workspace
title: Projects Overview
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
---
# Projects overview
 
Workspace projects allow you to combine panels, visualizations and components to craft your analysis and share with anyone in your organization. Before you start your first project, learn about how to access, navigate and manage your projects.  

To access projects in Adobe Analytics, select **[!UICONTROL Workspace]**.  The **[!UICONTROL Projects]** manager lists all the projects that you own or projects that are shared with you. The Project manager with the Project list is also the default landing page for Adobe Analytics, unless you have configured otherwise in Preferences. 

![Project landing page showing the projects list.](assets/projects.png)


## Title area

From within title area ➊ you can create a project, create a folder, edit your preferences and show or hide a panel with additional tiles.

* To show or hide a left panel that allows you to select between **[!UICONTROL Projects]** and **[!UICONTROL Learning]**, select ![Rail](/help/assets/icons/Rail.svg). 
* The title shows Projects, optionally added with a path to the folder you have selected. For example [!UICONTROL Projects] > **[!UICONTROL Company Folder]**. You can select individual subfolder parts to go directly to the specific folder. 
* To show tiles for a [**[!UICONTROL Blank project]**](create-projects.md), [**[!UICONTROL Blank mobile scorecard]**](/help/analyze/mobile-app/create-scorecard.md), **[!UICONTROL Open the documentation]** and **[!UICONTROL Open release notes]**, select ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Show more]**. To hide the area with tiles, select ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Show less]**.
* Based on what you select to show, using the [Show selector](#show-selector), you can edit preferences and perform actions on the current folder visible in **[!UICONTROL Projects]**:
  
  | Action | Description |
  |---|---|
  | **[!UICONTROL Create project]** | Select to [create a new project](create-projects.md). |
  |  **[!UICONTROL Create folder]** | Select to [create a new folder](workspace-folders/create-folders.md). |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Edit preferences]** | [Edit preferences](/help/analyze/analysis-workspace/user-preferences.md) for all your projects. When the breadcrumb results in limited space, this action is part of the ![More](/help/assets/icons/More.svg) submenu. |
  | **[!UICONTROL Add projects]** | Select to [add projects](workspace-folders/add-projects.md) to the current folder. When the breadcrumb results in limited space, this action is part of the ![More](/help/assets/icons/More.svg) submenu. |
  | **[!UICONTROL Rename folder]** | [Renames](workspace-folders/manage-folders.md#rename-folders) the current folder. |
  | **[!UICONTROL Move folder]** | [Moves](workspace-folders/manage-folders.md#move-folders) the current folder. |
  | **[!UICONTROL Delete folder]** | [Deletes](workspace-folders/manage-folders.md#delete-folders) the current folder. |

  


## Project list


The project list ➋ displays all the projects that you own and that have been shared with you. The list has the following columns:

| Column | Description |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | When one or more projects are selected, a blue action bar appears at the bottom of the Project interface. See [Actions](#actions) for more details. |
| ![StarOutline](/help/assets/icons/StarOutline.svg)  | Select to favor ![Star](/help/assets/icons/Star.svg) or un-favor ![StarOutline](/help/assets/icons/StarOutline.svg) a project. |
| **[!UICONTROL Title and description]** | To edit the project, select the title link, which opens the [Workspace project](/help/analyze/analysis-workspace/home.md). Projects shared with you are indicated with ![Share](/help/assets/icons/ShareAlt.svg). Select ![InfoOutline](/help/assets/icons/InfoOutline.svg) to display a popup menu with more details on the project. Select ![More](/help/assets/icons/More.svg) to open a context menu with actions. See [Actions](#actions) for more details. |
| **[!UICONTROL Type]** | A Workspace project, a ![FolderUser](/help/assets/icons/FolderUser.svg) folder, or a [Mobile Scorecard](/help/analyze/mobile-app/home.md). |
|  **[!UICONTROL Tags]**  | The tags applied to the project. |
| **[!UICONTROL Scheduled]** | Whether a project is scheduled o be emailed to recipients. Options are ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL On]** or ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Off]**. See [Send project data to others](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| **[!UICONTROL Shared link (anyone)]** | Whether a project is shared with anyone, even with people who don't have access to Analysis Workspace. Options are ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Active]** or ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Inactive]**. See [Share a project with anyone (no login required)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required) in [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md) for more information. |
| **[!UICONTROL Project Role]** | Your role for the project. Options are: Edit, Duplicate, View. See [Project roles](/help/analyze/analysis-workspace/curate-share/curate.md) for more information. |
| **[!UICONTROL Report Suite]** | The report suite that the project is associated with. |
| **[!UICONTROL Owner]**  | The person who created this project (either you or someone who shared the project with you.)  |
| **[!UICONTROL Shared with]**  | Users that the project has been shared with.  |
| **[!UICONTROL Last Modified]**  | Date and time when the project was last modified.  |
| **[!UICONTROL Last Opened]**  | Date and time when the project was last opened.  |
| **[!UICONTROL Component ID]**  | The ID of the component.  |
| **[!UICONTROL Longest Date Range]**  | The longest date range of any of the panels or visualizations in the project.  |
| **[!UICONTROL Number of Queries]**  | The total number of queries contained in the project.  |
| **[!UICONTROL Location]**  | The folder where the project resides.  |

Hover over any column header to display ![ChevronDown](/help/assets/icons/ChevronDown.svg) and select from the context menu:

* **[!UICONTROL Sort Ascending]**
* **[!UICONTROL Sort Descending]**
* **[!UICONTROL Resize column]**. A blue line appears to assist you to resize the column.

### Actions

You can take actions on one or more projects using the context menu ![More](/help/assets/icons/More.svg) or the blue action bar.

| Icon |Action  | Description |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg)| **[!UICONTROL *x* selected]** | Unselect your selected projects and folders and remove the blue action bar. |
| ![Delete](/help/assets/icons/Delete.svg) |**[!UICONTROL Delete]** | Delete one or more projects or folders. You are prompted for a confirmation. <p>Projects that you delete:</p><ul><li>Cannot be recovered</li><li>Are removed from the project list</li><li>Can no longer be accessed with their URL</li><li>Are no longer included in scheduled deliveries (in cases where they were previously configured for scheduled deliveries)<br/>For information about scheduled deliveries, see [Scheduled projects](/help/components/scheduled-projects-manager.md).  </p> |
| ![Share](/help/assets/icons/ShareAlt.svg) |**[!UICONTROL Share]** | Share a project. See [Share a project](/help/analyze/analysis-workspace/curate-share/share-projects.md) for more information. |
| ![Edit](/help/assets/icons/Edit.svg)| **[!UICONTROL Rename]** | Rename a project. Opens a **[!UICONTROL Rename: *project name dialog*]**. Enter a new name and select **[!UICONTROL Save]**. |
| ![Copy](/help/assets/icons/Copy.svg)| **[!UICONTROL Copy]** | Copy one or more projects. Project do get the same name and suffix `(Copy)`. |
| ![PinOnff](/help/assets/icons/PinOff.svg)| **[!UICONTROL Pin]** or **[!UICONTROL Unpin]** | Pin or unpin one or more projects or folders. Pinned projects and folders appear at the top of the list and ignore the sorting order you specify. |
| ![ArrowUp](/help/assets/icons/ArrowUp.svg)| **[!UICONTROL Move up]** | Move a pinned project or folder up in the project list.  |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg)| **[!UICONTROL Move down]** | Move a pinned project or folder down in the project list. |
| ![Label](/help/assets/icons/Label.svg)| **[!UICONTROL Tag]** | Tag one or more projects or folders. The **[!UICONTROL Tag Components]** dialog displays to select one or more tags. Select **[!UICONTROL Save]** to save the tags for the selected projects or folders. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)| **[!UICONTROL Approve]** or **[!UICONTROL Unapprove]** | Approve or unapprove a project. Only administrators can approve projects. |
|  ![FileCSV](/help/assets/icons/FileCSV.svg)| **[!UICONTROL Export CSV]** | Export the selected projects to a CSV file with name `Project List.csv`. |
|  ![ProjectAdd](/help/assets/icons/ProjectAdd.svg)| **[!UICONTROL Add Projects]** | Add one or more projects to a selected folder. In **[!UICONTROL Add Projects]** you can select one or more projects. Select **[!UICONTROL Add]** to add the projects to the folder. See [Add projects to folders](workspace-folders/add-projects.md#from-inside-a-folder) for more information. |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg)| **[!UICONTROL Move to]** | Move one or more selected projects to a folder. In the **[!UICONTROL Select Folder]**, select the folder to move the selected project to and select **[!UICONTROL Move]**. See [Add projects to folders](workspace-folders/add-projects.md#from-the-project-list) for more information. |



## Show selector

You can switch the look and feel of the Projects interface using the **[!UICONTROL Show]** selectors ➌. The **[!UICONTROL Show]** selector define what options are available in the [Title area](#title-area) and what columns are displayed in the [Project list](#project-list). 

* To change the options available for the [Title area](#title-area), select **[!UICONTROL Show]** **[!UICONTROL All projects]** or **[!UICONTROL Show]** **[!UICONTROL Folders & Projects]**.

* To define which columns to display for the [Project list](#project-list), select ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) and from the **[!UICONTROL Customize table]** dialog select or unselect columns. Select **[!UICONTROL Apply]** to apply the customization. See [Project list](#project-list) for more details on the columns.

## Filter panel

You can filter the projects and folders in the [Project list](#project-list) using the filter panel ➍. To show or hide the filter panel use ![Filter](/help/assets/icons/Filter.svg).

The filter panel consists of the following sections.

### Tags

| Tags   | Description |
|---|---|
| ![Tags](assets/projects-filters-tags.png){width="300"} | The **[!UICONTROL Tags]** section lets you filter on tags. <ul><li>You use ![Search](/help/assets/icons/Search.svg) *Search Tags* to search for tags you want to use to filter.</li><li>You can select more than one tag. The tags available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**2︎⃣**: The number of tags available for the projects resulting from the current filter.</li><li>7︎⃣: The number of projects associated with the specific tag.</li></ul></li></ul> |


### Report Suites

| Report Suites | Description |
|---|---|
| ![Report suite](assets/projects-filters-reportsuites.png){width="300"} | The **[!UICONTROL Report Suites]** section lets you filter on report suites. <ul><li>You use ![Search](/help/assets/icons/Search.svg) *Search Report Suites* to search for report suites you want to use to filter.</li><li>You can select more than one report suite. The report suites available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**3︎⃣**: The number of report suites available for the projects resulting from the current filter.</li><li>4︎⃣: The number of projects associated with the specific report suite.</li></ul></li></ul> |


### Owners

| Owner | Description |
|---|---|
| ![Owners](assets/projects-filters-owners.png){width="300"} | The **[!UICONTROL Owner]** section lets you filter on owners. <ul><li>You use ![Search](/help/assets/icons/Search.svg) *Search Owners* to search for owners you want to use to filter.</li><li>You can select more than one owner. The owners available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**3︎⃣**: The number of owners available for the projects resulting from the current filter.</li><li>4︎⃣: The number of projects associated with the specific owner.</li></ul></li></ul> |


### Type

| Type | Description |
|---|---|
| ![Type](assets/projects-filters-type.png){width="300"} | The **[!UICONTROL Type]** section lets you filter on the type of projects or folders.<ul><li>You can select one or more of the following options:<ul><li> **[!UICONTROL folder]**</li><li>**[!UICONTROL Workspace project]**</li><li>**[!UICONTROL Mobile scorecard]**</li></ul> <li>You can select more than one other filter. The other filters available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**5︎⃣**: The number of other filters available for the projects resulting from the current filter.</li><li>4︎⃣: The number of projects associated with the specific other filter.</li></ul></li></ul> |


### Other filters 

| Other filters | Description |
|---|---|
| ![Other filters](assets/projects-filters-others.png){width="300"} | The **[!UICONTROL Other filters]** section lets you filter on other predefined filter.<ul><li>You can select one or more of the following options:<ul><li> **[!UICONTROL Show all]**</li><li>**[!UICONTROL Shared with me]**</li><li>**[!UICONTROL Mine]**</li><li>**[!UICONTROL Approved]**</li><li>**[!UICONTROL Favorites]**</li></ul> What you can select depends on your role and permissions.</li><li>You can select more than one other filter. The other filters available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**5︎⃣**: The number of other filters available for the projects resulting from the current filter.</li><li>4︎⃣: The number of projects associated with the specific other filter.</li></ul></li></ul> |

## Search 

You use the Search area ➎ to search for projects and folders using the ![Search](/help/assets/icons/Search.svg) field. Start typing and the [project list](#project-list) automatically filters on your search input.

The Search area also shows the filters applied from the Filter panel. 

* To remove a filter, select ![CrossSize75](/help/assets/icons/CrossSize75.svg) in the filter.
* To remove all filters, select Clear all.

If space is limited to display the individual filters, you see **[!UICONTROL Segmenting by *x* filters]**. 

* To remove a filter:
  
  1. Use **[!UICONTROL *x* filters]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) top open a context menu listing the types of filters and the individual filters.
  1. Use ![CrossSize75](/help/assets/icons/CrossSize75.svg) to remove a filter.

