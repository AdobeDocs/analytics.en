---
description: Learn about sceduling macro-enabled workbooks.
title: About macro-enabled workbook scheduling
uuid: 874cfac8-ca63-4dec-b2aa-a3dcd037c5c5
feature: Report Builder
role: User, Admin
exl-id: 34b8ffc7-646a-4472-a99a-4b8876ea7b16
TQID: https://experienceleague.adobe.com/9LFw7NCIWaFALUD5TfCMiv2x3H7VkXf6zB4J8jyt1fk
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
# Schedule macro-enabled workbooks

{{legacy-arb}}

Adobe Report Builder supports the .xlsm format that lets you schedule macro-enabled workbooks.

This is useful if you need to safely schedule, process, and receive macro-enabled workbooks.

>[!IMPORTANT]
>
>Even though Report Builder lets you schedule workbooks with macros, these macros are not exercised during each scheduled run. They are only exercised when the workbook is open within the native Microsoft Excel application.

Scheduled workbooks with macros can only be delivered in macro-enabled format (.xlsm), because all other supported formats (xls, xlsx, pdf, word, csv, or txt) would remove the macros from the workbook.
