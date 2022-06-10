---
title: Visual Basic macros in Report Builder
description: Expand the functionality of Excel workbooks and Report Builder using VBA.
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
---
# Visual Basic macros in Report Builder

VBA macros, also known as Visual Basic macros, allow you to manipulate workbooks in ways Microsoft Excel alone cannot. Visual Basic has access to the workbook, Excel, and even Windows.

Adobe supports three Report Builder API methods. Ensure that the latest version of report builder is installed, and log in before running any macros.

>[!IMPORTANT]
>
>For security reasons, you cannot schedule a workbook that contains a macro.

## `RefreshAllReportBuilderRequests()`

The `RefreshAllReportBuilderRequests()` macro refreshes all Report Builder requests in the active workbook. It starts by calling the Report Builder COM Add-in through its Product ID, then calls the `RefreshAllRequests()` API command:

```vba
Sub RefreshAllReportBuilderRequests()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshAllRequests(ActiveWorkbook)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInActiveWorksheet()`

The `RefreshAllReportBuilderRequestsInActiveWorksheet()` macro refreshes all Report Builder requests in the active worksheet. The `RefreshWorksheetRequests()` API call takes a worksheet object as an argument. You can use this call for any worksheet that contains Report Builder requests:

```vba
Sub RefreshAllReportBuilderRequestsInActiveWorksheet()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshWorksheetRequests(ActiveWorkbook.ActiveSheet)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInCellsRange()`

The `RefreshAllReportBuilderRequestsInCellsRange()` macro refreshes all Report Builder requests whose cell outputs intersect the specified range of cells. The cell range used in this example points to the range `B1:B54` of the "Data" worksheet within the active workbook. The range expression supports all supported Excel range expressions:

```vba
Sub RefreshAllReportBuilderRequestsInCellsRange()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshRequestsInCellsRange("'Data'!B1:B54")
  
End Sub
```
