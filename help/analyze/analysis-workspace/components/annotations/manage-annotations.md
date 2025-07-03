---
title: Manage Annotations
description: Learn how to manage annotations in Analysis Workspace.
role: User, Admin
feature: Annotations
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
---
# Manage annotations

You can share, filter, tag, approve, copy, delete annotations and mark annotations as favorite from a central [!UICONTROL Annotations] management interface. To manage annotations:

* Select **[!UICONTROL Components]** in the main interface, then select **[!UICONTROL Annotations]**.


>[!NOTE]
>
>The annotations that you create within a specific Workspace project do not appear in the [!UICONTROL Annotations] manager, unless you have made the annotation available to all your projects. 
>

## Annotations manager

The Annotations manager has the following interface elements:

![Annotations interface](assets/annotations-manager.png)

### Annotations list

The annotations list ➊ displays all the annotations that you own, the annotations that have been scoped to all your projects, and the annotations that have been shared with you. The list has the following columns:

| Column | Description |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg)  | Select to favor ![Star](/help/assets/icons/Star.svg) or un-favor ![StarOutline](/help/assets/icons/StarOutline.svg) an annotation. |
| **[!UICONTROL Title and description]** | Provided in the Annotations Builder. To edit the title and description, select the title link - opens the [Annotations builder](/help/analyze/analysis-workspace/components/annotations/create-annotations.md#annotation-builder). A shared annotation is indicated with ![Share](/help/assets/icons/ShareAlt.svg).   |
| **[!UICONTROL Report suite]** | The report suites that this annotation applies to.  | 
| **[!UICONTROL Owner]** | The owner of the annotation. As a user, you only see the annotations that you own or the annotations that are shared with you. |
| **[!UICONTROL Applied date range]** | The date or date range that this annotation applies to. |
| **[!UICONTROL Tags]** | The tags for this annotation. |
| **[!UICONTROL Shared with]** | The individuals or groups that you shared the annotation with. Select to open the **[!UICONTROL Share Component]** dialog. |
| **[!UICONTROL Date modified]** | Displays the date and time that the annotation was last modified. |

{style="table-layout:auto"}

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to specify which columns you want to display.

### Action bar

You can action on annotations using the action bar ➋. The action bar contains the following actions:

| Icon| Action | Description |
|:--:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Add]** | Add another annotation, using the [Annotation builder](create-annotations.md#annotation-builder). |
| ![Search](/help/assets/icons/Search.svg) | [!UICONTROL *Search by title*] | When no annotation is selected in the list, search for annotations using this search field. |
| ![Label](/help/assets/icons/Label.svg)| **[!UICONTROL Tag]** | Tag the selected annotations. In the **[!UICONTROL Tag Component]** dialog, select or de-select the tags for the selected annotations. Select **[!UICONTROL Save]** to save the tags for the selected annotations. |
| ![Share](/help/assets/icons/ShareAlt.svg)| **[!UICONTROL Share]** | Share the selected annotations. In the **[!UICONTROL Share Component]** dialog, you can ![Search](/help/assets/icons/Search.svg) *Search individuals or groups* or you can select **[!UICONTROL Organization]** or **[!UICONTROL Groups]**. Select **[!UICONTROL Save]** to save share details for the selected annotations. See [Share annotations](#share-annotations) for more details. |
| ![Delete](/help/assets/icons/Delete.svg)| **[!UICONTROL Delete]** | Delete the selected annotations. You are prompted for a confirmation. |
| ![Edit](/help/assets/icons/Edit.svg)| **[!UICONTROL Rename]** | Rename a single selected annotation. When selected, you can rename the annotation inline. |
| ![Copy](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Copy the selected annotations. New annotations are created with the same name and suffix (Copy) | 
| ![FileCSV](/help/assets/icons/FileCSV.svg)| **[!UICONTROL Export to CSV]** | Export the annotations to an `Annotations List.csv` file. |

### Active filter bar

The filter bar ➌ shows the active filters (if any). You can quickly remove a filter using ![CrossSize75](/help/assets/icons/CrossSize75.svg). If more than one filter is specified, you can remove all filters using **[!UICONTROL Remove all]**.

### Filter panel

You can filter annotations using the  **[!UICONTROL Filter]** left panel ➍. The filter panel displays the type of filter and the number of annotations that honor the filter. Select ![Filter](/help/assets/icons/Filter.svg) to toggle the display of the filter panel. 

To filter the list of filters:

1. Select ![Filter](/help/assets/icons/Filter.svg) to open the Filters panel. If you need more space for the Filters list, you can select ![Filter](/help/assets/icons/Filter.svg) once more to close the panel.
1. You can filter the annotations using any of the available [filter sections](#filter-sections). 

   >[!INFO]
   >
   >*Items* refer to the annotation items displayed in the [Annotations list](manage-annotations.md#annotations-list).
   > 

#### Filter sections

{{tagfiltersection}}
{{reportsuitefiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


The [Annotations list](manage-annotations.md#annotations-list) is automatically updated based on your filter configuration. You can see the configured filters in the [Active filter bar](manage-annotations.md#active-filter-bar).


## Edit annotations

You can edit an annotation in two ways:

* In a Workspace project, use the [Component info](/help/analyze/analysis-workspace/components/use-components-in-workspace.md#component-info) icon.

* In the [[!UICONTROL Annotations] list](#annotations-list), select the title of the annotation.

You use the [Annotation builder](/help/analyze/analysis-workspace/components/annotations/create-annotations.md#annotation-builder) to edit the annotation.

## Share annotations

The following applies when sharing annotations or working with annotations that are shared with you:

* Project-only annotations in a project you share with other users are displayed for those users. The users cannot edit or delete these project-only annotations.
* If you save an annotation and share the annotation directly with a user, that user can edit and delete the annotation only if that user has admin rights.

* If a project is shared with you, annotations created in that project show up only in that project. If an annotation is shared directly with you, the annotation shows up in all projects where that annotation can be displayed. 

## Annotations and time zones

All annotations are created with a timestamp, but no hour or timezone information. At report time, the timezone of the report suite configured for the panel is used.


<!--
# Manage annotations

The [!UICONTROL Annotations manager] shows you all of the annotations that you own or that have been shared with you. Project-specific annotations do not appear here. You can use this interface to share, filter, tag, copy, delete, and favorite your annotations. Administrators can manage and approve annotations.

**[!UICONTROL Components]** > **[!UICONTROL Annotations]**

## Annotations Manager user interface

![](assets/annotation-mgr.png)

| UI Element | Description |
| --- | --- | 
| [!UICONTROL Title and Description] | Provided in the Annotations Builder. To edit the title and description, click the title link - this takes you back to the Annotations Builder.  |
| [!UICONTROL Report Suite] | The report suites that this annotation applies to.  | 
| [!UICONTROL Owner] | Indicates who owns the annotation. As a non-Admin, you can see only annotations that you own or those that were shared with you. |
| [!UICONTROL Applied Date Range] | The date or date range that this annotation applies to. |
| [!UICONTROL Shared with] | Lists how many individuals or groups that you shared the annotation with. Click for more detail. |
| [!UICONTROL Date Modified] | Shows the date and time that the annotation was last modified. |

{style="table-layout:auto"}

## Edit annotations

Editing an annotation means that you can adjust date ranges, colors, scope, or whether it applies to all report suites or projects. You can edit annotations in two ways:

* In a line chart, hover over the annotation and click the pencil icon within the popover.
* In the [!UICONTROL Annotations Manager], click the title of the annotation.

Both of these options land you back in the [!UICONTROL Annotations Builder]. There, you can make the necessary adjustments and save the new version.

## Share annotations

When sharing annotations or working with annotations that were shared with you, keep this in mind:

* If you create a project with project-only annotations, then share the project with another user, annotations cannot be edited or deleted by anyone that you share the project with.
* If you save an annotation and share it directly with a user, they can edit/delete the annotation only if they have admin rights.
* If a project is shared with you with a project-only annotation, it shows up only in that project. If the annotation is shared directly with you, it shows up in all projects where that annotation can be displayed. 

## Annotations and time zones

All annotations are created with a timestamp, but no hours or timezone information. At report time, the timezone of the panel's report suite is always applied. For example, an annotation created for Christmas Day happens on December 25 no matter what report suite timezone you are in. 

## Other annotation tasks

The Annotations manager lets Administrators edit, add, tag, delete, rename, approve, copy, export, and filter annotations. It is not visible to non-Admin users. 

Additional options are available when you select at least one annotation:

| Task | Description |
| --- | --- |
| [!UICONTROL Add] | Takes you to the Annotations builder where you can create annotations. |
| [!UICONTROL Tag] | All users can create tags for annotations and apply one or more tags to an annotation. However, you can see tags only for annotations that you own. |
| [!UICONTROL Delete] | Deleting an annotation removes it from any project in your organization. |
| [!UICONTROL Rename] | Renaming an annotation renames it in all projects that it was applied to. |
| [!UICONTROL Copy] | Creates a distinct copy with its own annotation ID, but with the same name and definition.|
| [!UICONTROL Export to CSV] | Export the annotation definition to a .csv file.|
| [!UICONTROL Filter] (left rail) | Filter by tags, report suite, owners, and other filters (Mine, Approved, Favorites, Shared with me, and Show All).|

{style="table-layout:auto"}

-->