---
description: Learn how to copy a spreadsheet from a source workbook to one or more target workbooks.
title: How to copy requests and worksheets between workbooks
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
feature: Report Builder
role: User, Admin
exl-id: 1a2363da-603e-4d1d-aefa-14ce71554247
---
# Copy requests and worksheets between workbooks

Copy an entire spreadsheet in a source workbook to a spreadsheet in one or more target workbooks. To do this, you must have at least two workbooks opened in the same instance of Excel: 
*  The first source workbook contains a spreadsheet (worksheet) with requests mapped to cells.
*  The additional target workbooks are the destinations. For each new target workbook, you should log in to the same report suite as the source workbook before you can paste spreadsheets containing requests.

>[!NOTE]
>
>You must log in to the target workbook using the same report suite as the source workbook. The requests in both workbooks must be created using the same report suite login.

1. Right-click the spreadsheet in the source workbook and select **[!UICONTROL Copy Worksheet w/Requests]**.
1. In the destination workbook, right-click the spreadsheet and select **[!UICONTROL Paste Worksheet w/Requests]**.

   The same instance of Excel means that only a single Excel process ( [!DNL excel.exe]) is running on your computer at a time. If you launch two instances of Excel and attempt to copy a worksheet from a workbook in the first instance of Excel to a workbook in the second instance of Excel, Report Builder does not present the option to paste a worksheet in the shortcut menu of the second instance of Excel.

   If you log in to the source and target workbooks using different report suites, the only results you see from the paste operation are those affecting the formatting of the target workbook. Report Builder displays a message stating that the information for the requests derived from a specified report suite (in the source workbook) is not available in the target workbook. To reveal the requests pasted to the target workbook, you must log in to the target workbook using the same report suite as the source workbook.

   You can copy and paste one or more requests from a spreadsheet in one workbook to a spreadsheet in another workbook, as long as the second workbook is open as another document in the same instance of Excel. The requests in both workbooks must be created using the same report suite login.
