---
title: How to manage data blocks using Report Builder
description: Describes how to use the manage feature in Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 63e169b3-7e13-405e-83a4-17f2a9917ed2
---
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
