---
description: In the same way that you copy and paste requests, you can also relocate requests to another part of the spreadsheet by selecting Cut Request from the shortcut menu.
title: Copy adjacent requests
topic: Report builder
uuid: c8abec0d-6fbd-4a98-8672-ede81317487b
---

# Copy adjacent requests

In the same way that you copy and paste requests, you can also relocate requests to another part of the spreadsheet by selecting Cut Request from the shortcut menu.

Cutting a request removes it from its original location and places it in the new location after you select [!UICONTROL Paste Request]. If you change your mind after cutting a particular request and decide to copy or cut a different request from another cell, Report Builder leaves the first request in its original cell and only acts (either copies or cuts) the second.

> [!NOTE] Report builder does not support the Excel Undo command for cutting or pasting requests. Therefore, be careful when cutting requests.

You are not limited to copying and pasting in the same sheet of the workbook. You can copy a request in one sheet and paste to a location in another sheet of the same workbook.

You are not limited to copying and pasting one request at a time. You can select more than one request in the spreadsheet and paste them to an empty region of the spreadsheet. Just as with copying and pasting one request, make sure that the paste region has no cells with requests that will be replaced by the paste operation. If the system finds that the target paste region already contains one or more requests, report builder does not display the [!UICONTROL Paste Requests] menu for any copied or cut requests. You must select a different cell as the destination of the paste operation so that requests do not overlap.
