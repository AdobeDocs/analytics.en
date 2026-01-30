---
title: Manage Data Blocks In Report Builder
description: Learn how to manage data blocks in Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 63e169b3-7e13-405e-83a4-17f2a9917ed2
---
# Manage data blocks

You can view and manage all data blocks in a workbook using the [!UICONTROL Data block manager]. The [!UICONTROL Data block manager] provides search, filter, and sort capabilities that allow you to locate specific data blocks. After selecting one or more data blocks, you can edit, delete, or refresh the selected data blocks.

## View data blocks

To view a table that lists all data blocks in a workbook, select ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]**.

   ![The Manage option to view a list of all data blocks.](./assets/image53.png){zoomable="yes"}

The **[!UICONTROL Data block manager]** shows a table with all data blocks present in a workbook.

![The list of all data blocks present in a workbook.](./assets/image52.png){zoomable="yes"}

You can use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to select which columns you want to display.

## Sort data blocks

You can sort the data block table by a displayed column. For example, you can sort data blocks by report suites, segments, date range, and other variables.

To sort the data block table, select a column heading. Select the same column heading to reverse the sort order.


## Search data blocks

Use the ![Search](/help/assets/icons/Search.svg) **[!UICONTROL _Search_]** field to locate anything in the data block table. For example, you could search for metrics contained in the data blocks or report suite. You can also search for dates appearing in the date range, date modified, or last run date columns.


## Edit data blocks

You can edit report suites and date ranges fordata blocks. Or the segments applied to data blocks.

For example, you can replace an existing segment with a new segment in one or more data blocks.

1. Select the data blocks that you want to update. You can select the top-level check box to select all data blocks or you can select individual data blocks.

   ![The pencil edit icon](./assets/image56.png){zoomable="yes"}

1. Select ![Edit](/help/assets/icons/Edit.svg) to display the **[!UICONTROL Quick edit]** window.

   ![The Quick edit window](./assets/image58.png){zoomable="yes"}

1. Select a link to update report suites, date ranges, or segments. In **[!UICONTROL Quick Edit]** - **[!UICONTROL Segments]** you can add, remove or update the segments for the selected data blocks.

   ![The Add Segment field in the Quick edit window](./assets/image59.png){zoomable="yes"}

## Refresh data blocks

Select ![Refresh](/help/assets/icons/Refresh.svg) to refresh the data blocks table.

To verify if a data block is refreshed, view the refresh status icon: 

- A successfully refreshed data block displays a ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg).

- A data block that has failed to refresh displays a ![AlertRed](/help/assets/icons/AlertRed.svg).


## Delete data blocks

To delete one or more data blocks:

1. Select one or more data blocks.
1. Select ![Delete](/help/assets/icons/Delete.svg). 
1. Select **[!UICONTROL Delete]** in the **[!UICONTROL Delete data block]** dialog or **[!UICONTROL Cancel]** to cancel the deletion.

## Group data blocks

You can group data blocks using the **[!UICONTROL Group by]** drop-down menu or you can select a column title. 

To sort data blocks by column, select the column title. To group data blocks by groups, select a group name from the **[!UICONTROL Group by]** drop-down menu. For example, the screenshot below shows data blocks grouped by Report suite. 

You can use grouping to select quickly data blocks for which you want to modify a common element, like segment.

![Data block manager showing the Group by Sheet list.](./assets/group-data-blocks.png){zoomable="yes"}



<!--

# Manage Data Blocks in Report Builder

You can view and manage all data blocks in a workbook using the Data Block Manager. The Data Block Manager provides search, filter, and sort capabilities that allow you to quickly locate specific data blocks. After selecting one or more data blocks, you can edit, delete, or refresh the selected data blocks.

![The Data block manager screen.](./assets/image52.png)

## View Data Blocks

Click **Manage** to view a list of all data blocks in a workbook.

![The Manage option to view a list of all data blocks.](./assets/image53.png)

The Data Block Manager lists all data blocks present in a workbook. 

## Sort the Data Blocks list

You can sort the data block list by a displayed column. For example, you can sort the data block list by report suites, segments, date range, and other variables.

To sort the data block list, click a column heading.

![Sorting the data blocks.](./assets/image54.png)

## Search the Data Block list

Use the Search field to locate anything in the data block table. For example, you could search for metrics contained in the data blocks or report suite. You can also search for dates appearing in the date range, date modified, or last run date columns.

![Using the Search field to locate anything in the data block table.](./assets/image55.png)

## Edit Data Blocks

You can edit the report suite, date range, or the segments applied to one or more data blocks.

For example, you can replace an existing segment with a new segment in one or more data blocks.

1. Select the data blocks that you want to update. You can select the top-level check box to select all data blocks or you can select individual data blocks.

   ![The pencil edit icon](./assets/image56.png)

1. Click the edit icon to display the Quick edit window.

   ![The Quick edit window](./assets/image58.png)

1. Select a segment link to update report suites, date ranges, or segments.

   ![The Add Segment field in the Quick edit window](./assets/image59.png)

## Refresh Data Blocks

Click the refresh icon to refresh the data blocks in the list.

<img src="./assets/refresh-icon.png" width="15%" alt="Refresh icon"/>

To verify if a data block is refreshed, view the refresh status icon. 

A successfully refreshed data block displays a checkmark in a green circle: <img src="./assets/refresh-success.png" width="5%" alt="Green circle with check mark icon"/>. 

A data block that has failed to refresh displays a warning icon: <img src="./assets/refresh-failure.png" width="5%" alt="Red triangle with exclamation mark icon"/>.This makes it easy to identify if any data blocks have errors.


![Data block manager showing refresh status for each data block listed.](./assets/image512.png)

## Delete a Data Block

1. Select a data block in the Data Block manager. 
1. Click the trash can icon to delete the selected data block.

## Group Data Blocks

You can group data blocks using the **Group by** drop-down menu or you can click a column title. To sort data blocks by column, click the column title. To group data blocks by groups, select a group name from the **Group by** drop-down menu. For example, the screenshot below shows data blocks grouped by Sheet. It shows data blocks grouped by Sheet1 and Sheet2.  This is useful, for example, in the segment-replacing use case. If you have multiple segments applied to each data block, it is helpful to create a group containing all the data blocks that you want to replace. Then you can easily select and edit them all at once.

![Data block manager showing the Group by Sheet list.](./assets/group-data-blocks.png)

## Modify the Data Block Manager view

You can modify which columns are visible in the Data Block Manager window.


Click the column list <img src="./assets/image515.png" width="3%" alt="Column list icon"/> icon to select which columns are listed in the Data Block Manager. Select a column name to display the column. Deselect the column name to remove the column from view.

![Data block manager showing the column list](./assets/image516.png)

-->