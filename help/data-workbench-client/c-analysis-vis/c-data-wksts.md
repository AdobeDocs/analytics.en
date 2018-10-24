---
description: Text or expressions can be entered into any cell of a worksheet.
seo-description: Text or expressions can be entered into any cell of a worksheet.
seo-title: Work with data in worksheets
solution: Analytics
title: Work with data in worksheets
topic: Data workbench
uuid: f311446f-f463-42c6-9231-3a62c2d930db
index: y
internal: n
snippet: y
---

# Work with data in worksheets

Text or expressions can be entered into any cell of a worksheet.

 All expressions in a worksheet are preceded by an equal sign (=) unless using [!DNL eval( )], which treats the text in the referenced cell as a expression.

For a full list of metric, dimension, and filter syntax rules, see [Query Language Syntax](../../data-workbench-client/c-qry-lang-syntx/c-qry-lang-syntx.md#concept_15D1D3F5164A47D49468C5ACB7299D9F).

**To type data into a worksheet**

1. Click twice on a cell in the spreadsheet to enter edit mode. The selected cell is highlighted. 
1. Type or paste the desired data into the cell.

**To copy and paste from one cell to another**

1. Right-click the cell containing the data that you want to copy and click **[!UICONTROL Copy]**. 
1. Right-click the cell into which you want to paste the copied data and click **[!UICONTROL Paste]**.

[!DNL Data workbench] automatically updates the references in the new cell to refer to the appropriate columns and rows.

**To copy and paste from a group of cells to another**

1. Select the cells containing the data that you want to copy. 
1. Right-click the cells containing the data that you want to copy and click **[!UICONTROL Copy]**. 
1. Right-click the first cell into which you want to start pasting the copied data and click **[!UICONTROL Paste]**. The data is pasted into the first cell and below it.

[!DNL Data workbench] automatically updates the references in the new cell to refer to the appropriate columns and rows.

**To insert a column**

* Right-click a column and click **[!UICONTROL Insert Column]**. The new column is inserted to the left of the selected column.

**To delete a column**

* Right-click the column that you want to delete and click **[!UICONTROL Delete Column]**. The column is removed.

**To insert a row**

* Right-click a row and click **[!UICONTROL Insert Row]**. The new row is inserted above the selected row.

**To delete a row**

* Right-click the row that you want to delete and click **[!UICONTROL Delete Row]**. The row is removed.

**To resize a column**

1. In the column header row, place your cursor over the dividing line to the right of the column whose size you want to change. 
1. Click and drag to the right to increase the width of the column, or to the left to reduce the width of the column.

**To format a cell**

1. Right-click the cell and click **[!UICONTROL Format]**.

   ![](assets/mnu_Worksheet_Format.png)

1. Click the desired format in the menu of available options:

<table id="table_5788E01E52CC44E7927A0D23760D9EDD"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Menu Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Number </p> </td> 
   <td colname="col2"> <p>Applies the selected numeric format to your data, such as time, date, percentage, or decimal. </p> <p>Click <span class="uicontrol"> Default</span> to remove the selected formatting. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Justify </p> </td> 
   <td colname="col2"> <p>Justifies the data within the cell to the left, center, or right. The default justification is left. </p> <p>Click <span class="uicontrol"> Default</span> to remove the selected formatting. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Color </p> </td> 
   <td colname="col2"> <p>Applies the selected font color to the data within the cell. The default font color is white. </p> <p>Click <span class="uicontrol"> Default</span> to remove the selected formatting. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Indicator </p> </td> 
   <td colname="col2"> <p>Creates a metric indicator using this cell. For more information, see <a href="../../data-workbench-client/c-analysis-vis/c-wksts/c-metric-ind.md#concept_F0E911B23B2C4E8DA3E1EA7B9AE04183" format="dita" scope="local"> Creating Metric Indicators</a>. </p> <p>Click <span class="uicontrol"> Default</span> to remove the selected formatting. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Input Cell </p> </td> 
   <td colname="col2"> <p>Makes the selected cell an input cell. For more information, see <a href="../../data-workbench-client/c-analysis-vis/c-wksts/c-input-cells.md#concept_08CD2C05A28A43DD9F7698B37E23E590" format="dita" scope="local"> Creating Input Cells</a>. </p> <p>Click <span class="uicontrol"> Default</span> to remove the selected formatting. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Keyboard shortcuts {#section_05301F4D2C60418E86902635A7AEEE20}

Within worksheets you can use many of the basic editing keyboard shortcuts that you can use in any text editor, such as Notepad or Microsoft Word.

The following table lists the basic keyboard shortcuts that you can use when entering data into a worksheet.

<table id="table_8E6F73F253B3451CA1DE45EE4F4E69EF"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Shortcut </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Arrow Keys </p> </td> 
   <td colname="col2"> <p>Move from cell to cell in your worksheet using the up, down, left and right arrow keys. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>F2 </p> </td> 
   <td colname="col2"> <p>Edit the cell by placing your cursor in the cell that you have selected. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Enter </p> </td> 
   <td colname="col2"> <p>Completes the editing of the cell that you have selected. Your cursor is removed from the cell and the cell contents reflect your editing. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Esc </p> </td> 
   <td colname="col2"> <p>Cancel the editing of the cell that you have selected. Your cursor is removed from the cell and the cell contents revert to what they were before you began editing. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Delete </p> </td> 
   <td colname="col2"> <p>Delete the contents of the cell(s). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Ctrl+A </p> </td> 
   <td colname="col2"> <p>Select the contents of the cell. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Ctrl+c </p> </td> 
   <td colname="col2"> <p>Copy the contents of the cell(s). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Ctrl+x </p> <p>Shift+Delete </p> </td> 
   <td colname="col2"> <p>Copy and remove the contents of the cell(s). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Ctrl+v </p> <p>Shift+Insert </p> </td> 
   <td colname="col2"> <p>Paste the contents of cell(s) that you have copied into the selected cell(s). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Ctrl+z </p> </td> 
   <td colname="col2"> <p>Undo typing. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Ctrl+Shift+z </p> </td> 
   <td colname="col2"> <p>Redo typing. </p> </td> 
  </tr> 
 </tbody> 
</table>

