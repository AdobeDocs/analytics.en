---
title: Report Builder Hub
description: Learn about the Report Builder hub.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: e18381ea-b7d4-4d7a-9ded-23b2d06fa204
---
# Report Builder hub


The Report Builder hub is the right pane that is displayed within your Excel workbook when you select ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** from the Excel ribbon bar.

Use the Report Builder hub to create, update, delete, and manage data blocks.

The Report Builder hub contains the  ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**, ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** and ![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]** buttons, the **[!UICONTROL Commands]** panel, and the **[!UICONTROL Quick edit]** panel.

![Report Builder hub](assets/hub51.png){zoomable="yes"}


Select

* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]** to [create new data blocks](create-a-data-block.md).  
* ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** to [manage existing data blocks](manage-reportbuilder.md).
* ![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]** to [manage schedules to send your workbook by email](schedule-reportbuilder.md).

## Commands panel

Use the **[!UICONTROL Commands]** panel to access commands that are compatible with the selected cells or a previous action.

| Commands      | Available when…   | Purpose          |
|------|------------------|--------|
| ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit data block]** | The selected cell or cells range is part of one data block only. | Use to edit a data block.                       |
| ![Refresh](/help/assets/icons/Refresh.svg) **[!UICONTROL Refresh data block]**      | The selection contains at least one data block. The command refreshes only the data blocks in the selection. | Use to refresh one or more data blocks.    |
| ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Refresh all data blocks]** | The workbook contains one or more data blocks. | Use to refresh all data blocks in the workbook |
| ![Send](/help/assets/icons/Send.svg) **[!UICONTROL Send workbook]** | The workbook contains one or more data blocks. | Use to [send the workbook as a file by email](schedule-reportbuilder.md). |
| ![Copy](/help/assets/icons/Copy.svg) **[!UICONTROL Copy data block]**   | The selected cell or cell range is part of one or more data blocks. | Use to copy a data block.   |
| ![Cut](/help/assets/icons/Cut.svg) **[!UICONTROL Cut data block]** | The selected cell or cell range is part of one or more data blocks. | se to cut a data block. |
| ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete data block]** | The selected cell or cells range is part of one data block only. | Use to delete a data block |

## Quick edit panel

When you select one or more data blocks in a spreadsheet, Report Builder displays the **[!UICONTROL Quick edit]** panel. You can use the **[!UICONTROL Quick edit]** panel to change parameters in one or more data blocks at the same time.

The changes you make when you use the **[!UICONTROL Quick Edit]** sections apply to all selected data blocks.

### Report suites

Data blocks pull data from a selected report suite. If multiple data blocks are selected in a worksheet and they don't pull data from the same report suite, the **Report suites** link displays **[!UICONTROL _Multiple_]**.

When you change the report suite, all data blocks in the selection adopt the new report suite. Components in the data block are matched to the new report suite based on ID. If a component isn't found in a data block, the component is removed and replaced with **[!UICONTROL Invalid value]** or an ![AlertRed](/help/assets/icons/AlertRed.svg) is displayed for the specific component.

To change the report suite, select a new report suite from the **[!UICONTROL Report suite]** drop-down menu.


### Date range

**Date range** shows the date range for the selected data blocks. If multiple data blocks are selected with multiple date ranges, the **[!UICONTROL Date range]** link displays **[!UICONTROL _Multiple_]**.

### Segments

The **Segments** link displays a summary list of the segments used by the selected data blocks. If multiple data blocks are selected with multiple segments applied, the **Segments** link displays **[!UICONTROL _Multiple_]**.

>[!MORELIKETHIS]
>
>[Select a report suite](select-report-suite.md)
>[Select a date range](select-date-range.md)
>[Work with filters](work-with-filters.md)
>

<!--

Use the Report Builder hub to create, update, delete, and manage data blocks.

The Report Builder hub contains the Create, Manage, and Schedule buttons, the COMMANDS panel, and The QUICK EDIT panel.

<img src="./assets/hub51.png" alt="Report Builder Hub"/>


## Create, Manage, and Schedule buttons

Use the Create, Manage, and Schedule buttons to create new data blocks, manage existing data blocks, or schedule datablocks.

## COMMANDS panel

Use the COMMANDS panel to access commands that are compatible with the selected cells or a previous action.

### Commands

| Commands displayed      | Available when…   | Purpose          |
|------|------------------|--------|
| Edit data block | The selected cell or cells range is part of one data block only. | Used to edit a data block |
| Refresh data block | The selection contains at least one data block. The command refreshes only the data blocks in the selection. | Used to refresh one or more data blocks |
| Refresh all data blocks | The workbook contains one or more data blocks. | Used to refresh ALL data blocks in the workbook |
| Send workbook |   |  Send a workbook on a schedule. |
| Copy data block   | The selected cell or cell range is part of one or more data blocks. | Used to copy a data block   |
| Cut data block |   | Used to cut a data block |
| Delete data block | The selected cell or cells range is part of one data block only. | Used to delete a data block |

## QUICK EDIT panel

When you select one or more data blocks in a spreadsheet, Report Builder displays the QUICK EDIT panel. You can use the QUICK EDIT panel to change parameters in a single data block or to change parameters in multiple data blocks at the same time.

![The Quick Edit panel in Report Builder](./assets/hub2.png)

The changes made using the Quick Edit sections apply to all selected data blocks.

### Report suites

Data blocks pull data from a selected report suite. If multiple data blocks are selected in a worksheet and they don't pull data from the same report suite, the **Report Suites** link displays *Multiple*.

When you change the report suite, all data blocks in the selection adopt the new report suite. Components in the data block are matched to the new report suite based on ID, for example, matching ```evars```). If a component isn't found in a data block, a warning message is displayed and the component is removed from the data block.

To change the report suite, select a new report suite from the drop-down menu.

![The Report Builder Hub showing the report suite drop-down menu.](./assets/image16.png)

### Date range

**[!UICONTROL Date range]** shows the date range for the selected data blocks. If multiple data blocks are selected with multiple date ranges, the **[!UICONTROL Date range]** link displays *Multiple*. [Learn more](/help/analyze/report-builder/select-date-range.md)

### Segments

The **Segments** link displays a summary list of the segments used by the selected data blocks. If multiple data blocks are selected with multiple segments applied, the **Segments** link displays *Multiple*. [Learn more](/help/analyze/report-builder/work-with-segments.md)

-->