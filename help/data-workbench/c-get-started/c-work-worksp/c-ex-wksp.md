---
description: You can export a workspace as a .png image file or export the data from certain windows to an Excel (.xls or .xlsx) file.
seo-description: You can export a workspace as a .png image file or export the data from certain windows to an Excel (.xls or .xlsx) file.
seo-title: Export a workspace
solution: Analytics
title: Export a workspace
topic: Data workbench
uuid: 9caaf854-48ed-4dd2-a3a0-692fbb3396ee
index: y
internal: n
snippet: y
---

# Export a workspace

You can export a workspace as a .png image file or export the data from certain windows to an Excel (.xls or .xlsx) file.

## Export a workspaces as a PNG file {#section_F9FBE0F0A1C341E2B063CCE106CAC35E}

You can save a snapshot of a workspace in Portable Network Graphic format ( [!DNL .png] files). The following color options are available when saving workspaces as [!DNL .png] files:

* **Black background** copies the workspace as displayed. 
* **White background** copies the elements of the workspace in color and displays them on a white background. 
* **White background (B&W)** copies the elements of the workspace in grayscale and displays them on a white background.

**To export a workspace as a .png file**

In the title bar menu of a workspace, click **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *< **[!UICONTROL color option]**>*.

The [!UICONTROL Save Image As] dialog box appears.

Navigate to the directory in which you want to save the file, change the name of the file if necessary, and click **[!UICONTROL Save]**.

## Export workspace data to Microsoft Excel {#section_FE214E3DBC364D2EBA3834D62D295ACB}

When exporting a workspace to Excel, Data Workbench exports data from certain visualizations, dimension and value legends, and text annotations to a new Excel workbook with one visualization per worksheet.

To export workspaces and individual windows to Microsoft Excel, the following requirements must be met:

* Microsoft Excel must be installed on the same machine as Data Workbench. 
* The user account under which the Data Workbench process is running must have permission to access Microsoft Excel.

>[!NOTE]
>
>* When you export data as Excel files, you are opening a new instance of Excel. For more information about this process, see [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757). 
>* Although Data Workbench supports more than 256 columns and 65,536 rows of data, versions of Microsoft Excel prior to 8.0 do not. 
>

If these requirements are met, Data Workbench automatically starts Microsoft Excel and export the data to a new Excel workbook. Data is not exported from the following visualizations: graphs, path browsers, process maps, scatter plots, and globes.

## Apply custom titles {#section_A332E157554546CB8E88922A8D7A4FA2}

Unless you have specified a Custom title for the window on the [!UICONTROL Export] menu, the [!UICONTROL Export title] listed (for example, City Table) is used as the worksheet name.

1. Right-click the top border of the window and click in the **[!UICONTROL Custom title]** field. 
1. Type the title that you want to apply to the window.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>If you enter a hyphen (-) in the [!UICONTROL Custom title] field, this visualization is not exported with the workspace.

When you export the workspace to Excel, the worksheet containing the data for this window is named using the title that you specified instead of the title in the [!UICONTROL Export title] field.

## Export a workspace or sidebar to Excel {#section_360438B66D5F4734826AB463B4A01A75}

**To export workspace data to a new [!DNL .xls] or [!DNL .xlsx] file**

1. In title bar of the workspace, click **[!UICONTROL Export]** > **[!UICONTROL Export]**. 
1. Specify whether to export the workspace, sidebar, or both.

## Export to a template Excel file {#section_814772929CA64CF6B92B89D3FDD02302}

You can export data in your workspace to a template Excel file ( [!DNL .xls] or [!DNL .xlsx]). Using a template file can reduce the amount of time that you spend formatting your data each time the workspace is exported.

>[!NOTE]
>
>This template file must be an [!DNL .xls] or [!DNL .xlsx] file, not an [!DNL .xlt] file.

When the data is exported, the existing tabbed sheets in the template (each representing one visualization) are repopulated with the most recent data from the workspace, while any new windows that are not present in the template as tabbed sheets are ignored. Any other tabbed sheets in the template file remain unchanged.

In addition, if you have a macro defined in the template Excel file that you would like to run automatically when the report is generated, name the macro “VSExport.”

Let’s say that you want to use exported campaign data from a table visualization in a pie chart on another tabbed sheet in an Excel file and want to update this information every week. You can use a template so that you do not have to recreate your references from the table’s tabbed sheet to the pie chart’s tabbed sheet each time you want to update the data. The table data is updated upon export, which automatically updates the pie chart.

**To export workspace data to a template [!DNL .xls] or [!DNL .xlsx] file**

1. Right-click the title bar of the workspace and click **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**. 
1. Specify whether to export a workspace, sidebar, or both.

   The [!UICONTROL Select a template worksheet] dialog box opens. 

1. Complete one of the following steps as appropriate:

    * If you are using a [!DNL .xls] template file:

        1. Browse to and select the template [!DNL .xls] file. 
        1. Click **[!UICONTROL Open]**.

    * If you are using a [!DNL .xlsx] template file:

        1. Browse to the location of the template file. The [!DNL .xlsx] file name is not displayed. 
        1. In the [!UICONTROL File name] field, type [!DNL *.xlsx] and click **[!UICONTROL Open]**. All [!DNL .xlsx] file names display in the file list. 
        
        1. Select the template [!DNL .xlsx] file. 
        1. Click **[!UICONTROL Open]**.

