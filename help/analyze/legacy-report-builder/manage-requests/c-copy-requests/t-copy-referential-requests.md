---
description: Learn how to copy referential requests.
title: How to copy referential requests
feature: Report Builder
role: User, Admin
exl-id: 3cd77325-7461-4345-a672-64c03ea1ae5b
TQID: https://experienceleague.adobe.com/A-ef3rd0b7WMBRqBgmxFWpa35x8R7qYF1dMkF5gx5Ec
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
# Copy referential requests

{{legacy-arb}}

A referential request uses values from cells as input for parameters, such as a data filter or relational filter.

To propagate or copy and paste referential requests in the spreadsheet:

*  You must create at least one valid request in the spreadsheet.

*  The data produced by the request must contain a cell whose value is dependent on either a request in another cell (using a breakdown or matching filter) or dependent on a filter that takes input from data entered in a cell.

You can also create requests that reference input filters from requests in different worksheets, but not different workbooks. For example, a request in Sheet 2 can use a report suite from a given cell in Sheet 1 and a date range from a cell in a request in Sheet 2. The new output can be placed in either sheet or a new sheet within the same workbook. When you paste a relative request, if an input filter resides on a worksheet different from the worksheet on which the copied request output is located, the filter is pasted as an absolute filter.

>[!NOTE]
>
>You can't output a single request in multiple worksheets. In addition, the system can't paste some of the copied requests into new workbooks because the requests contain input filters from other worksheets. Input filters include report suites from cells, date ranges from cells, filters from cells, and other related parameters.

**To copy referential requests** 

1. Select the cells containing requests you want to copy, including the input cell or referred to cell.
1. Right-click within the highlighted cells and select **[!UICONTROL Copy Requests]** from the shortcut menu.

   After selecting the area where requests and input cells are located, the system highlights the cells with these elements.
1. Select either one cell or a range of contiguous cells to fill with the pasted requests.

   Make sure that the cell or cell range that you select contains no other data or requests.
1. Right-click the single cell or the top left-most cell in the range of cells and select **[!UICONTROL Paste Requests]**.

   When pasting requests that include an input cell, the options under [!UICONTROL Paste Requests] include:

   **Use Absolute Input Cell:** Pastes a copy of the request(s) and formatting associated with the selected cells to the paste region you highlight. The input cell (the cell referred to in one of the original requests) is not pasted. Instead, the input cell remains in the same position as before.

   **Use Relative Input Cell:** Pastes a copy of the request(s) and formatting associated with the selected cells to the paste region you highlighted, including a copy of the input cell. The spatial relationship of the request(s) to the input cell is the same as in the original request(s). However, while the newly pasted cells now have a copy of the requests, they have no content initially. This is because when the input cell is recreated in the paste operation, no data is associated with the input cell. To display data for the newly pasted request(s), you must enter a value in the input cell and then refresh the request(s).
