---
description: Copy a simple request rather than a referential request. A simple request is one that contains no references to another request or the contents of a cell.
title: Copy simple requests
uuid: ff20560a-01ee-47e7-8bd1-b73edb010456
feature: Report Builder
role: User, Admin
exl-id: ceed28d5-cb7f-4343-96fd-2ce09f5a3515
---
# Copy simple requests

Copy a simple request rather than a referential request. A simple request is one that contains no references to another request or the contents of a cell.

 A [referential request](/help/analyze/report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md) uses values from cells as input for parameters, such as a data filter or relational filter. These filters use either matching or trending and are based on results of a prior request or on the user-entered contents of a cell, called an input cell .
1. Create a valid request.
1. Right click one of the cells where the request is mapped, or select a region of cells containing requests.

   Be consistent in choosing a cell to copy from in the group of cells covered by the request. The preferred choice is the top and left-most cell of the set of cells covered by the request, and work from left to right. This is because the Excel spreadsheet has hundreds of columns and thousands of rows available for rightward and downward expansion. If you do decide to start a request copy from the rightmost or bottom cell in a set of cells associated with a request, the system does not allow you to paste the request if the cells to be pasted will extend beyond the left or top border of the spreadsheet.
1. Select **[!UICONTROL Copy Request]**.
1. In another part of the spreadsheet, right click on an empty cell (a cell containing no request).

   To prevent you from losing or corrupting requests you have already created, you cannot paste cells containing requests to cells currently mapped with requests. If you copy or cut cells containing requests, the shortcut menu does not make the [!UICONTROL Paste Requests] option available when right clicking on cells (or the set of cells) containing requests. You must select a different cell as the destination of the paste operation so that requests do not overlap. This applies whether you select a single cell with a request to paste or a region of cells containing requests.
1. Click **[!UICONTROL Paste Request]**.

   A copy of the original request is placed in the cell(s), in a position or positions relative to the original request.

   >[!NOTE]
   >
   >Only requests are copied, not the contents of the cells. If you have other information not based on requests, but relevant to understanding the data displayed in the cells (such as table column headers or row identifiers), use Excel's standard commands Copy and Paste.

   Because Excel uses different clipboards for copying cell contents and copying requests, you can copy both non-request cell contents and then requests by performing a Copy/Paste and Copy Requests/Paste Requests in series. However, if you apply formatting to requests in the spreadsheet and then copy and paste, report builder reproduces the original formatting (such as borders, fonts, etc.) in the paste region.

   Modifying a request that you have copied or cut to the clipboard before pasting the request removes the request from the clipboard. Therefore, to keep the request in its original state, do not modify a request between the time you copy it and the time you paste it.
