---
title: Select A Data Range In Report Builder
description: Learn how to select a date range in Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 610ce2c8-8ff6-4434-912f-3015cc56a51e
---
# Select a date range

To change the date range of an existing data block:

- Select **[!UICONTROL Edit a data block]**, or
- Select the **[!UICONTROL Date range]** link in **[!UICONTROL Quick edit]**.

Use the following options to change a date range for a data block.

## Calendar

The **[!UICONTROL Calendar]** option allows you to create static or rolling dates using the following options:

### Date range

The date range field displays the current date range for the data block request. You can enter dates directly or use ![Calendar](/help/assets/icons/Calendar.svg) to specify a date range.

![Date range calendar](assets/date-range-calendar.png){zoomable="yes"}

### Presets

Use the presets drop-down menu to select a preset. You can also enter text to search for presets.

![Date range presets](assets/date-range-presets.png){zoomable="yes"}

The preset drop-down menu includes a standard set of preset date ranges and date range components for a report suite that you saved or a report suite that was shared with you.

### Rolling dates

To define rolling dates:

![USe rolling dates](assets/date-range-rolling-date.png){zoomable="yes"}

1. Select **[!UICONTROL Use rolling dates]** to define the logic for a rolling date definition. You can select the text in brackets (for example **[!UICONTROL fixed start - rolling daily]**) to extend the panel and specify details for **[!UICONTROL Start]** and **[!UICONTROL End]**.

1. Select **[!UICONTROL Start of]**, **[!UICONTROL End of]**, or **[!UICONTROL Fixed day]**.

   - When you have selected **[!UICONTROL Start of]** or **[!UICONTROL End of]**, you can build a full expression. For example: **[!UICONTROL End of]** **[!UICONTROL current year]** **[!UICONTROL plus]** `1` **[!UICONTROL day]**. Pick the appropriate value for each individual part of the expression.
  
     - Select a value for current. For example, **[!UICONTROL current year]**.
     - Select a value for an optional additional calculation. For example, **[!UICONTROL plus]**.
     - When you have specified an additional calculation, specify a value. For example, `1`.
     - When you have specified an additional calculation, select the time period to use for the calculation. For example, **[!UICONTROL day]**.

   - When you have select **[!UICONTROL Fixed Day]**, specify a fixed day or use the picker to select a day.
     
1. Select **[!UICONTROL hide]** to hide the details for rolling dates calculation.


### Custom expressions

The custom expression option allows you to change the date range by building a custom expression or you can enter an arithmetic formula.

![Date range custom expression](assets/date-range-custom-expression.png){zoomable="yes"}

1. Select **[!UICONTROL Use rolling dates]**.

1. Select **[!UICONTROL Use custom expression]**.

    When you select **[!UICONTROL Use custom expression]**, the standard rolling date range controls are disabled.

1. Enter a [custom expression](#create-a-custom-expression).

1. Use the **[!UICONTROL Date preview]** to verify the resulting date range.

#### Create a custom expression

1. Enter a [date reference](#date-references).

1. Add an optional [date operator](#date-operators) to move the date to the past or future.

You can enter a custom expression that includes multiple operators, such as `tm-11m-1d`.

#### Date references

The following table lists date reference examples.

| Date reference | Type         | Description                |
|----------------|--------------|----------------------------|
| `1/1/10`         | Static Date  | Entered in ISO Date format |
| `td`             | Rolling Date | Start of current day       |
| `tw`             | Rolling Date | Start of current week      |
| `tm`             | Rolling Date | Start of current month     |
| `tq`             | Rolling Date | Start of current quarter   |
| `ty`             | Rolling Date | Start of current year      |

#### Date operators

The following table lists date operator examples.

| Date operator | Unit    | Description   |
|----------------|---------|--------------------|
| `+6d`            | Day     | Add 6 days to the Date Reference |
| `+1w`            | Week    | Add one full week to the Date Reference |
| `-2m`            | Month   | Subtract 2 full months to the Date Reference |
| `-4q`            | Quarter | Subtract 4 quarters to the Date Reference |
| -`1y`            | Year    | Subtract one year to the Date Reference |

#### Date expressions

The following table lists date expression examples.

| Date Expression | Meaning                              |
|-----------------|--------------------------------------|
| `td`              | Today                                |
| `td-1w`           | First day of last week               |
| `tm-1d`           | Last day of previous month           |
| `td-52w`          | Same day, 52 weeks ago               |
| `tm-11m-1d`       | Last day of the same month last year |
| `"2020-09-06"`    | Specific date, Sept 9th, 2020                       |



## Date range from cell

The date range can be specified in worksheet cells. Use the **[!UICONTROL Date range from cell]** option to choose the data block start and end date from selected cells. When you select the **[!UICONTROL From cell]** option, the panel displays **[!UICONTROL From]** and **[!UICONTROL To]** fields where you can enter a cell location or use ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) to pick the current selected cell.

![Select From cell Sheet1!H4 to Sheet1!I4](./assets/date-range-from-cell.png){zoomable="yes"}


## Exclude today

Select **[!UICONTROL Exclude today]** to exclude today from a selected date range. The current day is excluded from all modes used to define a date range: calendar, rolling dates, or custom expressions.


## Valid date ranges

The following list describes valid date range formats.

- The start and end dates must be in the following format: YYYY-MM-DD

- The start date must be earlier to or equal to the end date. Both dates can be set to the future.

- When using rolling dates, the start date must be today or in the past. The start day must be in the past if **[!UICONTROL Exclude today]** is selected.

- You can create a static date range set for the future. For example, you may need to set a future date for a marketing campaign launch next week. This option creates a workbook monitoring for a campaign ahead of time.

## Change the date range

You can edit the date range of an existing data block. 

1. Select a cell in your data block. 

- Select **[!UICONTROL Edit data block]** in the **[!UICONTROL Commands]** panel, or 
- Select the **[!UICONTROL Date range]** link in the **[!UICONTROL Quick edit]** panel. 
  
1. Modify the date range using any of the date selection options available.

1. Select **[!UICONTROL Apply]**.

Report Builder applies the new date range to all data blocks in the selection.

<!--
To change the date range of an existing data block, select Edit a data block or use the QUICK EDIT panel.

Use the following options to change a date range for a data block.

**Calendar**

 The Calendar allows you to create static or rolling dates using the following options:

- Date range field
- Calendar
- Preset drop-down menu
- Rolling date mode
- Customize expressions


**From cell**

The **[!UICONTROL From cell]** option allows you to reference dates entered in worksheet cells.

You have the option to exclude today on any selected date range.

 ![Report Builder Quick edit pane with calendar selected and Exclude today selected.](./assets/image17.png)

## Use the Calendar

When you use the **Calendar**, the date range field displays the current date range for the data block request. You can enter dates directly into the date range field or use a data range selection option.

### Date range field

To enter dates directly into the date range field

1. Click the date range field next to the calendar icon.

1. Enter start and end dates for your date range.

### Calendar

To select dates using the calendar

1. Click the calendar icon to display a monthly calendar.

1. Click a start date.

1. Click an end date.

To set a date range in reverse, click the end date first and then click the start date.

![Report Builder date range pane showing the calendar and the end date and the start date selected.](./assets/image18.png)

### Preset drop down menu

The preset drop-down menu includes a standard set of preset date ranges and date range components for a report suite that you saved or a report suite that was shared with you.

### Rolling dates

The rolling dates option allows you to select a date range using rolling dates.

1. Select **Use rolling dates**.

1. Select a rolling expression for your start and or end date.

    ![Report Builder date range pane showing Use rolling dates selected and the rolling expression.](./assets/image19.png)

    **Start of** — Allows you to select the beginning of a day, week, month, quarter, or year.

    **End of** — Allows you to select the end of a day, week, month, quarter, or year.

    **Fixed day** — Allows you to fix a start or end date while the other date is rolling.

1. Choose day, week, month, quarter, or year as the rolling period.

    ![Report Builder date range pane showing the current day selected.](./assets/image20.png)

1. Add or subtract days, weeks, months, quarters, or years from your rolling date.

    ![Report Builder date range pane showing the current day plus 14 days selected.](./assets/image21.png)

1. Click Next to define the data range.

    Use the date preview to confirm the resulting date range is the desired range.

### Custom expressions

The custom expression option allows you to change the date range by building a custom expression or you can enter an arithmetic formula.

1. Select **Use rolling dates**.

1. Select **Use custom expression**.

    When you select the **Use custom expression** option, the standard rolling date range controls are disabled.

    ![Select Use custom expression showing tm-1m to td-1d.](./assets/custom_expression.png)

1. Enter a custom expression.

    For a sample list of custom expressions, see **Date expressions**.

1. Use the date preview to verify the resulting date range is the desired range.

#### Create a custom expression

1. Enter a **Date reference**.

1. Add **Date operators** to move the date to the past or future.

You can enter a custom date expression that includes multiple operators, such as ```tm-11m-1d```.

#### Date references

The following table lists date reference examples.

| Date Reference | Type         | Description                |
|----------------|--------------|----------------------------|
| 1/1/10         | Static Date  | Entered in ISO Date format |
| td             | Rolling Date | Start of current day       |
| tw             | Rolling Date | Start of current week      |
| tm             | Rolling Date | Start of current month     |
| tq             | Rolling Date | Start of current quarter   |
| ty             | Rolling Date | Start of current year      |

#### Date operators

The following table lists date operator examples.

| Date Operators | Unit    | Description   |
|----------------|---------|--------------------|
| +6d            | Day     | Add 6 days to the Date Reference |
| +1w            | Week    | Add one full week to the Date Reference |
| -2m            | Month   | Subtract 2 full months to the Date Reference |
| -4q            | Quarter | Subtract 4 quarters to the Date Reference |
| -1y            | Year    | Subtract one year to the Date Reference |

#### Date expressions

The following table lists date expression examples.

| Date Expression | Meaning                              |
|-----------------|--------------------------------------|
| td-1w           | First day of last week               |
| tm-1d           | Last day of previous month           |
| td-52w          | Same day, 52 weeks ago               |
| tm-11m-1d       | Last day of the same month last year |
| "2020-09-06"    | Sept 9th, 2020                       |

## Date range from cell

The date range can be specified in worksheet cells. Use the **Date range from cell** option to choose the data block start and end date from selected cells. When you select the **From cell** option, the panel displays **From** and **To** fields where you can enter a cell location.

![Select From cell Sheet1!H4 to Sheet1!I4](./assets/image23.png)

## Exclude today

Choose the **Exclude today** option to exclude today from a selected date range. Choosing to include today may pull incomplete data for today.

When selected, the **Exclude today** option excludes the current day from all date range modes including calendar, rolling dates, or custom expressions.

## Valid date ranges

The following list describe valid date range formats.

- The start and end dates must be in the following format: YYYY-MM-DD

- The start date must be earlier to or equal to the end date. Both dates can be set to the future.

- When using rolling dates, the start date must be today or in the past. It must be in the past if **Exclude today** is checked.

- You can create a static date range set for the future. For example, you may need to set a future date for a marketing campaign launch next week. This option creates a workbook monitoring for a campaign ahead of time.

## Change the date range

You can edit the date range of an existing data block by selecting Edit data block in the COMMANDS panel or by selecting the date range link in the QUICK EDIT panel.

**Edit data block** — Allows you to edit multiple data block parameters, including date range, for a single data block.

**Quick Edit: Date range** — Allows you to edit the date range of one or more data blocks.

To edit the date range from the QUICK EDIT panel

1. Select cells within one or more data blocks in a worksheet.

1. Click the **Date range** link in the QUICK EDIT panel.

1. Select the date range using any of the date selection options.

1. Click **Apply**.


Report Builder applies the new date range to all data blocks in the selection.
-->