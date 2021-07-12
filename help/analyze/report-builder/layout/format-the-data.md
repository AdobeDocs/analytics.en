---
description: In addition to the standard cell formatting choices available through Excel's Format > Cells (Ctrl+1) feature, you can apply limited formatting to cell ranges with report builder. These formatting choices depend on the metric you have chosen.
title: Format the date
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
---
# Format the date

In addition to the standard cell formatting choices available through Excel's Format > Cells (Ctrl+1) feature, you can apply limited formatting to cell ranges with report builder. These formatting choices depend on the metric you have chosen.

After you [add dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) to the Row Labels grid, click **[!UICONTROL Format]**.

In the **[!UICONTROL Format]** menu, click **[!UICONTROL Custom Format]** to apply customized formats for dates similar to the prepend and postpend feature. For example, you can enter text that always occurs after the date (such as A.D. B.C.E. A.H. etc.). You can add text before the date, such as [!UICONTROL Start Date] and [!UICONTROL Start and End Date]. In addition, you can construct a custom date expression from day, month, and year abbreviations, and use a custom separator between parts of the date. All date formats must consist of three abbreviations only enclosed in brackets.

The following table describes how you can use date abbreviations in the [!UICONTROL Custom Format] field: 

| Abbreviation  | Meaning  | Example   using Wednesday, March 14, 2012  |
|--- |--- |--- |
|MM/dd/yyy|Full numeric date|03/14/2012|
|M|Number of month|3|
|MM|Number of month with 0 padding for months < 10|03|
|MMM|Short name of month|Mar|
|MMMM|Long name of month|March|
|D|Long name of the date|Wednesday, March 14, 2012|
|d|Number of day|14|
|dd|Number of day with 0 padding for days < 10|01 - 09|
|ddd|Short name of day|Wed|
|dddd|Long name of day|Wednesday|
|yy|2-digit year|10|
|yyyy|Full 4-digit year|2012|
