---
title: Manage Classification Sets Consolidations
description: Learn how to consolidate one or more classification sets into a single classification set.
exl-id: 0be97ca4-56c3-4642-9347-924812e88e8c
feature: Classifications
---
# Manage classification sets consolidations

If you have multiple classification sets that contain similar classification data, you can consolidate them into a single classification set. When you consolidate two or more classification sets, Adobe generates a new classification set that contains all classification data from each individual classification set. Consolidations are useful when you have uploaded data to many report suites or dimensions that contain the same classification data and would like to merge them into a single workflow. You must have product admin access for Adobe Analytics to see the Classification set consolidation manager.



To manage classification sets consolidations:

1. Select **[!UICONTROL Components]** in the main interface, then select **[!UICONTROL Classification sets]**.
1. In **[!UICONTROL Classification Sets]**, select the **[!UICONTROL Consolidations]** tab.
   

## Classification consolidations manager

The **[!UICONTROL Classification Sets Consolidations]** manager has the following interface elements:

![Classifications Sets - Consolidations Manager](assets/classifications-sets-consolidations.png)



### Classification sets consolidations list

The **[!UICONTROL Classification Sets Consolidations]** list ➊ displays classification sets consolidations that are created and validated, and that might be consolidating  . The list has the following columns:

| Column | Description |
|---|---|
| **[!UICONTROL Consolidation Name]** | The name of the classification sets consolidation. |
| **[!UICONTROL Current Job]** | The job associated with the classification sets consolidation. |
| **[!UICONTROL Status]** | The status of the classification sets consolidation. Possible values are: **[!UICONTROL Created]**, **[!UICONTROL Canceled]**, **[!UICONTROL Canceling]**, **[!UICONTROL Validating]**, **[!UICONTROL Failed Validation]**, **[!UICONTROL Validated]**, **[!UICONTROL Comparing]**, **[!UICONTROL Comparison Failed]**, **[!UICONTROL Consolidation]**, **[!UICONTROL Submitted]**, **[!UICONTROL Consolidating]**, **[!UICONTROL Consolidation Failed]**, **[!UICONTROL Consolidation Succeeded]**, **[!UICONTROL Waiting for Approval]**, **[!UICONTROL Finalizing]**, **[!UICONTROL Failed]**, or **[!UICONTROL Completed]**.  |
| **[!UICONTROL Creation time]** | The creation time of the classification sets consolidation. |
| **[!UICONTROL Completion Time]** | The completion time of the classification sets consolidations. |


### Search and buttons

In the area ➋ on top of the classification sets consolidations list, you can:

* Search ![Search](/help/assets/icons/Search.svg) for classification sets consolidations. Results are shown in the classification sets consolidations list. Select ![CrossSize200](/help/assets/icons/CrossSize200.svg) to clear the search.
* Create a new classification sets consolidation. Select ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]** to open the classification sets consolidation dialog and define a new classification sets consolidation.
* Define the columns of the classification sets consolidations list. Select ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) and in the **[!UICONTROL Customize table]** dialog select the columns to show underneath **[!UICONTROL Select columns to show]**. Select **[!UICONTROL Apply]** to apply the column settings.


### Action bar

When you select one or more classification set in the classification set list, a blue action bar ➌ appears. The following actions are available in the action bar:

| Icon | Action | Description |
|---|---|---|
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL Edit]** | [Edit the classification sets consolidation](process.md#edit-a-consolidation) |
| ![ViewDetail](/help/assets/icons/ViewDetail.svg) | **[!UICONTROL View]** | View details of the classification sets consolidation. Depending on the status you can [approve](process.md#approve) or [cancel](process.md#cancel) the consolidation. |


### Filter panel

Select ![Filter](/help/assets/icons/Filter.svg) to show the filter panel ➍ that allows you to filter the classification sets consolidations list. You can filter on:

* **[!UICONTROL Status]**. Select one of the possible values to filter the classification sets consolidations list on status. |
* **[!UICONTROL Completion Time]**. Select one of the possible values to filter the classification sets consolidations list on completion time.
* **[!UICONTROL Creation Time]**. Select one of the possible values to filter the classification sets consolidations list on completion time.


Select ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Hide filters]** to hide the filters panel.

Note that he filters shown in the filters panel reflect the options for the classification sets consolidations that are preloaded.


<!--

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]**

Once a consolidation is run, the original classification sets are removed, with the consolidated classification set taking their place. Click **[!UICONTROL Add]** to [Create a consolidation](process.md).

## Filter classification sets

The left side of the Classification set consolidation manager provides filter settings to locate the desired consolidation. Clicking the filter icon toggles the filter settings visibility. You can filter consolidations by **[!UICONTROL Status]**, **[!UICONTROL Completion time]**, or **[!UICONTROL Creation time]**.

![Classification set consolidation filters](../../assets/classification-set-consolidation-filters.png)

Additional filter options are available above the Classification set consolidation manager columns:

* **[!UICONTROL Search by title]**: Search for consolidations by name.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Name].

## Classification set consolidation manager columns

The following columns are available in the Classification set consolidation manager:

* **[!UICONTROL Name]**: The name of the consolidation.
* **[!UICONTROL Current job]**: The current job. 
* **[!UICONTROL Status]**: The status of the consolidation. 
* **[!UICONTROL Creation date]**: The date and time that the consolidation was created.
* **[!UICONTROL Completion date]**: The date and time that the consolidation completed (or failed).

-->
