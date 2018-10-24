---
description: You can export the data in certain windows to an Excel file (.xls or .xlsx) or to a tab separated values file (.tsv).
seo-description: You can export the data in certain windows to an Excel file (.xls or .xlsx) or to a tab separated values file (.tsv).
seo-title: Export window data
solution: Analytics
title: Export window data
topic: Data workbench
uuid: 8c0d9052-0e27-48d9-a1fe-1554e1de006f
index: y
internal: n
snippet: y
---

# Export window data

You can export the data in certain windows to an Excel file (.xls or .xlsx) or to a tab separated values file (.tsv).

Data is not exported from graphs, path browsers, process maps, scatter plots, and globes.

## Export window data to Microsoft Excel {#section_B660ADF7F4F64A2B9BE7287C591B67B0}

To export individual window data to Microsoft Excel, the following requirements must be met:

* Microsoft Excel must be installed on the same machine as Data Workbench. 
* The user account under which the Data Workbench process is running must have permission to access Microsoft Excel. 
* When you export data as Excel files, you are opening a new instance of Excel. 
* Although Data Workbench supports more than 256 columns and 65,536 rows of data, versions of Microsoft Excel prior to 8.0 do not.

If these requirements are met, Data Workbench automatically starts Microsoft Excel and export the data to a new Excel workbook when you select the **[!UICONTROL Export To Excel]** menu option.

**To export window data to an .xls or .xlsx file**

Right-click the top border of the window and click **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Excel opens a new workbook containing the exported data. Unless you have provided a Custom title (as described in the following section), this workbook is named using the [!UICONTROL Export title] (Day Table in the example above).

## Apply custom titles {#section_2A6559DF812A470685E43923B7B9024E}

If you provide a custom title for a window (using the [!UICONTROL Custom title] field on the [!UICONTROL Export] menu) the worksheet to which Data Workbench exports the data is named using this custom title instead of the title in the [!UICONTROL Export title] field (Day Table in the example above).

**To apply a custom title to a visualization**

1. Right-click the top border of the window and click in the **[!UICONTROL Custom title]** field. 
1. you

![](assets/mnu_window_TitleBar_Export.png)

When you export the visualization to Excel, the worksheet containing the data for this window is named using the title that you specified instead of the title in the [!UICONTROL Export title] field.

## Export window data to a TSV file {#section_93C6B24F7338430AAF5A63B99B9489E8}

**To export a window to a .tsv file**

Right-click the top border of the window and click **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. The [!UICONTROL Save Window] dialog box appears. 
1. Navigate to the directory in which you want to save the file. Change the name of the file if necessary, and click **[!UICONTROL Save]**.

