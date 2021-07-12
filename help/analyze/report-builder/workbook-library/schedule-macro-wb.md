---
description: Adobe Report Builder supports the .xlsm format that lets you schedule macro-enabled workbooks.
title: Schedule macro-enabled workbooks
uuid: 874cfac8-ca63-4dec-b2aa-a3dcd037c5c5
feature: Report Builder
role: User, Admin
exl-id: 34b8ffc7-646a-4472-a99a-4b8876ea7b16
---
# Schedule macro-enabled workbooks

Adobe Report Builder supports the .xlsm format that lets you schedule macro-enabled workbooks.

This can be useful if you need to safely schedule, process, and receive macro-enabled workbooks.

>[!IMPORTANT]
>
>Even though Report Builder lets you schedule workbooks with macros, these macros are not exercised during each scheduled run. They are only exercised when the workbook is open within the native Microsoft Excel application.

Scheduled workbooks with macros can only be delivered in macro-enabled format (.xlsm), because all other supported formats (xls, xlsx, pdf, word, csv, or txt) would remove the macros from the workbook.
