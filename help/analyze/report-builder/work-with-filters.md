---
title: How to use filters in Report Builder in Customer Journey Analytics
description: Describes how to use filters in Report Builder for Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
---
# Work with Filters in Report Builder

You can apply Filters when you create a new data block or when you select the **Edit data block** option from the COMMANDS panel.

## Apply filters to a data block

To apply a filter to the entire data block, double-click a filter or drag and drop filters from the components list into the Filters section of the Table.

## Apply filters to individual metrics

To apply filters to individual metrics, drag and drop a filter onto a metric in the table. You can also click the **...** icon to the right of a metric in the Table pane and then select **Filter metric**. To view applied filters, hover over or select a metric in the Table pane. Metrics with applied filters display a filter icon.

![Filters tab displaying metrics.](./assets/filter_by.png)

## Quick edit filters

You can use the Quick edit panel to add, remove, or replace filters for existing data blocks.

When you select a range of cells in the spreadsheet, the **Filters** link in the Quick edit panel displays a summary list of the filters used by the data blocks in that selection.

To edit filters using the Quick edit panel

1. Select a range of cells from one or multiple data blocks.

    ![Quick Edit filter panel showing filter options for data views, date range, and filters.](./assets/select_multiple_dbs.png)

1. Click the Filters link to launch the Quick edit - Filters panel.

    ![the Filters panel showing the Add Filter field and Filters Applied lists.](./assets/quick_edit_filters.png)

### Add or remove a filter

You can add or remove filters using the Add/Remove options.

1. Select the **Add/Remove** tab in the Quick edit-filters panel.

    All filters applied to the selected data blocks are listed in the Quick Edit-filters panel. Filters applied to all data blocks in the selection are listed under the **Applied to all selected data blocks** heading. Filters applied to some but not all data blocks are listed under the **Applied to 1 or more selected data blocks** heading.

    When multiple filters are present in the selected data blocks, you can search for specific filters using the **Add Filter** search field.

    ![The Add Filter field.](./assets/add_filter.png)

1. Add filters by selecting filters from the **Add filter** drop down menu.

    The list of searchable filters includes all filters accessible to the data views that are present in one or more of the selected data blocks as well as all the filters that are available globally in the organization.

    Adding a filter applies the filter to all data blocks in the selection.

1. To remove filters, click the delete icon **x** to the right of filters in the **Filters applied** list.

1. Click **Apply** to save changes and return to the hub panel.

    Report Builder displays a message to confirm the applied filter changes.

### Replace a filter

You can replace an existing filter with another filter to change how the data is filtered.

1. Select the **Replace** tab in the Quick edit-filters panel.

    ![Select the Replace tab.](./assets/replace_filter.png)

1. Use the **Search list** search field to locate specific filters.

1. Choose one or more filters that you want to replace.

1. Search for one or more filters in the Replace with field.

    Selecting a filter adds it to the **Replace with**... list.

    ![The Replace tab with the People on App data block selected and the Replace with list updated showing People on App Revised.](./assets/replace_screen_new.png)

1. Click **Apply**.

    Report Builder updates the list of filters to reflect the replacement.

### Define data block filters from cell

Data blocks can reference filters from a cell. Multiple data blocks can reference the same cell for filters, allowing you to easily switch filters for multiple data blocks at a time.

To apply filters from a cell

1. Navigate to Step 2 in either the data block creation or editing process. See [Create a Data Block](./create-a-data-block.md).
1. Click the **Filters** tab to define filters.
1. Click **Create filter from cell**.

    ![Create filter from cell icon.](./assets/create-filter-from-cell.png)

1. Select the cell from which you want the data blocks to reference a filter.
   
1. Add the filters choice you wish to add to the cell by either double clicking the filter, or by dragging and dropping it into the Filters Included section. 
   
   Note: Only one choice may be selected for the given cell at one time.

    ![The Add filter from cell window showing the Filters included.](./assets/select-filters.png)

1. Click **Apply** to create the reference cell.

1. From the **Filters** tab, add the newly created reference cell filter to your data block.

    ![Filters tab showing Sheet1!J1(All Data) filter added to the table.](./assets/reference-cell-filter.png)

1. Click **Finish**.

    Now this cell can be referenced by other data blocks in their filters. To apply the reference cell as a filter to other data blocks, simply add the cell reference to their filters from the filters tab. 

#### Use the reference cell to change data block filters

1. Select the reference cell in your spreadsheet.

1. Click the link under **Filters from Cell** in the Quick Edit menu.

    ![Filters from cell link showing Sheet1!J1 (All Data)](./assets/filters-from-cell-link.png)

1. Select your filter from the drop-down menu.

    ![Filter drop down menu](./assets/filter-drop-down.png)

1. Click **Apply**.
