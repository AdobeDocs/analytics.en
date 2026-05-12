---
description: Learn how to copy, paste, and relocate requests to another part of the spreadsheet.
title: How to copy adjacent requests
uuid: c8abec0d-6fbd-4a98-8672-ede81317487b
feature: Report Builder
role: User, Admin
exl-id: 99476ec5-f1f0-49f5-a2d8-354cec63c6b1
TQID: https://experienceleague.adobe.com/q1uVTribovAk-NJRXuAjW-kUIQfpquEPIbbOM9W8UmY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Copy adjacent requests

{{legacy-arb}}

In the same way that you copy and paste requests, you can also relocate requests to another part of the spreadsheet by selecting [!UICONTROL Cut Request] from the shortcut menu.

Cutting a request removes it from its original location and places it in the new location after you select [!UICONTROL Paste Request]. If you change your mind after cutting a particular request and decide to copy or cut a different request from another cell, Report Builder leaves the first request in its original cell and only acts (either copies or cuts) the second.

>[!NOTE]
>
>Report builder does not support the Excel Undo command for cutting or pasting requests.

You're not limited to copying and pasting in the same sheet of the workbook. You can copy a request in one sheet and paste to a location in another sheet in the same workbook.

You aren't limited to copying and pasting one request at a time. You can select more than one request in the spreadsheet and paste them to an empty region of the spreadsheet. Just as with copying and pasting one request, make sure that the paste region has no cells with requests that will be replaced by the paste operation. If the system finds that the target paste region already contains one or more requests, Report Builder does not display the [!UICONTROL Paste Requests] menu for any copied or cut requests. You must select a different cell as the destination of the paste operation so that requests do not overlap.
