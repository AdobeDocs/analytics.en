---
description: Learn how to use Microsoft Excel with Report Builder functions without accessing the Report Builder user interface.
title: Learn how to use Microsoft Excel with Report Builder functions
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
---
# Use Report Builder functions with Microsoft Excel

You can use Report Builder functions to access functionality without accessing the Report Builder user interface.

For example, to automatically refresh Report Builder requests with input filters based on data pulled into Excel from other sources, use the string RefreshRequestsInCellsRange(..) function. All calls are asynchronous and they return immediately and do not wait to fully execute.

**Requirements**

*  Report Builder 5.0 (or later) is required.

The following table lists the exposed functions.

|  Function Name  | Type |  Description  |
|:---| --- | ---|
|  AsyncRefreshAll()  | string | Refreshes all Report Builder requests present in a workbook.  |
|  AsyncRefreshRange(string rangeAddressInA1Format)  | string |  Refreshes all Report Builder requests present in the specified cell range address (a string expression representing a range of cell in A1 format, for example "Sheet1!A2:A10").  |
|  AsyncRefreshRangeAltTextParam()  | string |  Refreshes all Report Builder requests present in the specified cell range that is passed through the Alternative Text of the Ms Form Control.  |
|  AsyncRefreshActiveWorksheet()  | string |  Refreshes all Report Builder requests present in the active worksheet.  |
|  AsyncRefreshWorksheet(string worksheetName)  | string |  Refreshes all Report Builder requests present in the specified worksheet (the worksheet name as it appears on the tab.)  |
|  AsyncRefreshWorksheetAltTextParam();  | string |  Refreshes all Report Builder requests present in the specific worksheet name that was passed through the Alternative Text of the Ms Form Control  |
| tring GetLastRunStatus()  | string |  Returns a string that describes the status of the last run.  |

To access the Report Builder functions, go to **[!UICONTROL Formulas]** > **[!UICONTROL Insert Function]**. Use the search field to search for a function or select a category to list the functions in that category.

![Screenshot showing the Insert Function window with the category list expanded.](assets/arb_functions.png)

## Example {#section_034311081C8D4D7AA9275C1435A087CD}

The following example shows *If the value in cell P5 is text or is blank, refresh the range that is in cell P9*. 

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

## Use Report Builder functions with format control {#section_26123090B5BD49748C8D8ED7A1C5ED84}

You can assign a macro to a control you created and that control can be a function that refreshes a workbook request. For example, the function AsyncRefreshActiveWorksheet will refresh all requests in a worksheet. Sometimes, though, you may want to refresh only certain requests.

1. Set the macro parameter.
1. Right-click the control and select **[!UICONTROL Assign Macro]**.
1. Enter the Report Builder function name (no parameters or parentheses.)

![Screenshot showing the Assign Macro window.](assets/assign_macro.png)

## Pass parameters to Report Builder functions using format control {#section_ECCA1F4990D244619DFD79138064CEF0}

Two functions that take a parameter can be used with Format Control. You must use the **Alternative text:** field:

* AsyncRefreshRange(string rangeAddressInA1Format) 
* AsyncRefreshWorksheet(string worksheetName)

To pass parameters to Report Builder functions using format control

1. Right-click the control and select **[!UICONTROL Format Control]**.

   ![Screenshot showing Format Control selected.](assets/format_control.png)

1. Click the **[!UICONTROL Alt Text]** tab.

   ![Screenshot showing the Alt Text tab and Alternative text: field.](assets/alt_text.png)

1. Under **[!UICONTROL Alternative text]**, enter the cell range that you want refreshed.
1. Open the list of Report Builder parameters under **[!UICONTROL Formulas]** > **[!UICONTROL Insert Function]**> **[!UICONTROL Adobe.ReportBuilder.Bridge]**.

1. Pick one of the two functions that end with AltTextParam and click **[!UICONTROL OK]**.
