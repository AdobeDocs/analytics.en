---
description: The Segment manager offers many ways of curating segments, such as sharing, filtering, tagging, approving, copying, deleting, and marking as favorites.
title: Manage segments (Segment manager)
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
---
# Manage segments


You can [share](t-seg-share.md), [segment](t-seg-filter.md), [tag](seg-tag.md), [approve](seg-approve.md), rename, [copy](seg-copy.md), delete, export segments and mark segments as [favorite](t-seg-favorite.md) from a central [!UICONTROL Segment] management interface. To manage segments:

* Select **[!UICONTROL Components]** in the main interface, then select **[!UICONTROL Segments]**.


>[!NOTE]
>
>The quick segments that you create within a specific Workspace project do not appear in the [!UICONTROL Segment] manager, unless you have made the segment available to all your projects. 
>

## Segment manager

The Segment manager has the following interface elements:

![Segment interface](assets/segments-manager.png)

### Segment list

The segments list ➊ displays all the segments that you own, the segments that have been scoped to all your projects, and the segments that have been shared with you. The list has the following columns:

| Column | Description |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg)  | Select to favor ![Star](/help/assets/icons/Star.svg) or un-favor ![StarOutline](/help/assets/icons/StarOutline.svg) a segment. See [Mark segment as favorite](t-seg-favorite.md) |
| **[!UICONTROL Title and description]** | To edit the segment, select the title link, which opens the [Segment builder](seg-build.md). A shared segment is indicated with ![Share](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Report suitew]** | The report suite that this segment applies to.  | 
| **[!UICONTROL Owner]** | The owner of the segment. As a user, you only see the segments that you own or the annotations that are shared with you. |
| **[!UICONTROL Tags]** | The tags for this segment. |
| **[!UICONTROL Shared with]** | How many individuals or groups that you shared the segment with. Select to open the **[!UICONTROL Share Component]** dialog. See [Share segments](t-seg-share.md) for more information. |
| **[!UICONTROL Published]** | Whether the [segment is published](seg-publish.md) to Experience Cloud. |
| **[!UICONTROL Date modified]** | The date and time that the segment was last modified. |

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to specify which columns you want to display.

### Action bar

You can action on segments using the action bar ➋. The action bar contains the following actions:

| Action | Description |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Add another segment, using the [Segment builder](seg-build.md). |
| ![Search](/help/assets/icons/Search.svg) [!UICONTROL *Search by title*] | When no segment is selected in the list, search for segments using this search field. |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Tag the selected segments. In the **[!UICONTROL Tag Segment]** dialog, select or de-select the tags for the selected segments. Select **[!UICONTROL Save]** to save the tags for the selected segments. See [Tag segments](seg-tag.md) for more information.|
| ![Share](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share]** | Share the selected segments. In the **[!UICONTROL Share Segment]** dialog, you can ![Search](/help/assets/icons/Search.svg) *Search individuals or groups* or you can select **[!UICONTROL Organization]** or **[!UICONTROL Groups]**. Select **[!UICONTROL Save]** to save share details for the selected segments. See [Share segments](t-seg-share.md) for more information. |
| ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Delete the selected segments. You are prompted for a confirmation. |
| ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Rename a single selected segment. When selected, you can rename the segment inline. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Approve the selected segments. See [Approve segments](seg-approve.md) for more information. | 
| ![Copy](/help/assets/icons/Copy.svg)  **[!UICONTROL Copy]** | Copy the selected segment. New segments are created with the same name and suffix `(Copy)`. | 
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Export the segments to a `Segments List.csv` file. |

### Active filter bar

The filter bar ➌ shows the active segments applied from the filter panel to the list of segments (if any). You can quickly remove a filter using ![CrossSize75](/help/assets/icons/CrossSize75.svg). If more than one filter is specified, you can remove all filter using **[!UICONTROL Remove all]**.

### Filter panel

You can filter the list of segments using the ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** left panel ➍. The filter panel displays the type of filter and the number of segments that honor the specific filter. Select ![Filter](/help/assets/icons/Filter.svg) to toggle the display of the Filter panel. 

See [Filter the list of segments](t-seg-filter.md) for more information.


<!--

The Segment manager offers many ways of curating segments, such as sharing, filtering, tagging, approving, copying, deleting, and marking as favorites.

The Analytics Segment manager shows you all the segments you own and that have been shared with you. Admin-level users can see all segments in the organization. This overview presents the user interface and the capabilities of the Segment manager. 

![Segments manager](assets/segments-manager.png)

## Access the Segment manager

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**.

   Or 

   In an existing report, select the Segments icon ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) in the left navigation, then select **[!UICONTROL Manage]**.

## Available actions in the Segment manager

In the Segment manager, you can:

* [Filter segments](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [Approve segments](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [Tag segments](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [Share segments](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* Export a segment to a CSV file.

* [Copy segments](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [Delete segments](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## Configure columns

You can configure the information displayed for each segment in the Segment manager by configuring the columns that are displayed.

To configure the visible columns in the Segment manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**. 

1. In the Segment manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Segment manager.

   The following columns are available:

   | Column title | Description  |
   |---|---|
   | Title and description | These values are provided in the Segment builder. To edit the title and description, select the title link to open the Segment builder.  |
   | Favorites  | Displays star icons next to each segment, allowing you to mark segments as favorites. For more information, see [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | Report suites  | This column indicates in which report suite the segment was last saved.  |
   | Owner  | Indicates who owns the segment. As a non-Admin, you can see only segments you own or those that were shared with you.  |
   | Tags (not checked in column selector, hence column not appearing)  | Tags that were applied to the segment, either by you or by people who shared the segment with you.  |
   | Shared with  | Lists individuals or groups (Admin only) or All (Admin only) that you shared the segment with. <p>When a segment is being shared by you or with you, a share icon displays next to the segment name.</p>|
   | Date modified  | Shows the date that the segment was last modified.  |
   | Used in | Shows where segments are currently being used, and how many times they are being used in each area. <p>For example, if the segment is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**].</p> <p>Select the value in this column to see the breakdown of where the segments are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Alerts (2)**]). Furthermore, you can view the list of items where the segments are being used. For example, so see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of segments being used in that area:</p>  <ul><li>[!UICONTROL **Projects**]<p>Contains segments that were [created in the segment builder](/help/components/segmentation/segmentation-workflow/seg-build.md) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains segments that were [created as quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Alerts**]</li><li>[!UICONTROL **Calculated metrics**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a segment includes another segment in its definition, any use of that segment is not shown in the [!UICONTROL **Used in**] column. If a segment is included in the definition of another type of component (such as a calculated metric), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p>  |
   | Last used | Shows the date when the segment was last used in any of the following component types: <ul><li>Alerts</li><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li><li>Segments</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |
   
   {style="table-layout:auto"}

## How-To Video {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

This [Adobe Analytics video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html) gives a short overview of how to use the Segment manager.

-->