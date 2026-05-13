---
description: Learn how to apply conditional formatting to workbook cells.
title: About conditional formatting for workbooks
uuid: 13ac12f1-3498-4bf9-a6d0-c5d84e0125dc
feature: Report Builder
role: User, Admin
exl-id: 5a5f2415-8269-4c8a-9193-784537b29edf
TQID: https://experienceleague.adobe.com/UnZqnq2Y3D7AfZ6mM0xNVVr4F-wOKhqix4tTTo6BQg0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
    internal-label: Report Builder
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
---
# Specify conditional formatting

{{legacy-arb}}

After you create reports with embedded requests, you can apply conditional formatting to workbook cells.

On the Report Builder Toolbar, click **[!UICONTROL Format]**.

Conditional formatting lets you identify cells that contain results or values that you want to monitor. For example, you can apply red shading or highlighting to a particular cell if the revenue is below expectations, and blue shading if revenue exceeds amounts that you forecast. If a change in date ranges for requests removes conditions that cause conditional formatting to apply to cell values, the formats that highlight that condition are disabled temporarily. When the conditional formats you specify result in no change because conditions are not met, the conditional formats continue to apply to cells until you remove them.

For security reasons, macros are disabled if you write the workbook macros using Excel's Visual Basic for Applications (VBA) language.

>[!NOTE]
>
>Conditional formatting is an Excel feature. For information about creating formatting rules, see the Excel documentation.
