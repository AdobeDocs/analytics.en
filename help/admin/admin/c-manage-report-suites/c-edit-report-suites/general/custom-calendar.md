---
description: Calendar options in other than the Gregorian model. Options include the 4-4-5, 4-5-4, and 5-4-4 calendar models, all of which are used as standards for the retail industry. Additionally, reporting offers an option for a completely customizable calendar that you can set up yourself.
title: Customize Calendar
feature: Admin Tools
exl-id: 2196c7b7-7183-43a8-bb91-5a1e479819d4
---
# Customize Calendar

Calendar options in other than the Gregorian model. Options include the 4-4-5, 4-5-4, and 5-4-4 calendar models, all of which are used as standards for the retail industry. Additionally, reporting offers an option for a completely customizable calendar that you can set up yourself.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Select report suite > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Customize Calendar]**

>[!CAUTION]
>
>Changing the calendar changes the way data is processed (i.e. the definition of weekly and monthly unique visitors). When a calendar's definition of weeks and months changes, historical data is not altered. This setting also affects segments based on date ranges.

You can use the calendar to define the first day of the week and year, or use a different retail calendar style. The calendar formats are used to for various purposes, including sales comparison and forecast standardization, payroll cost analysis, or physical inventory count regulation. For example, the retail industry uses the 4-5-4 accounting calendar to support selling season's particular to the retail industry. Each of the calendar formats is described below.

## Customize Calendar Descriptions {#section_B0D224DACB914A378902A4E0E1234889}

|Calendar|Description|
|--- |--- |
|Gregorian Calendar|Uses the traditional calendar format (January through December, with 30 or 31 days and a variable number of weeks in each month).|
|Modified Gregorian Calendar|Uses the Traditional Gregorian Calendar but enables you to select the first month of the year and first day of the week.|
|4-5-4 Retail Calendar|Breaks down each month by the number of weeks in the month. Meaning, January has four weeks, and so on. The National Retail Federation uses the 4-5-4 calendar format.|
|Custom Calendar|Offers three formats based on the number of weeks in each month. The number of weeks in each month depends on the selected first day of the year.  A year has 52 weeks. Divide that into 4 quarters and you get 13 weeks per quarter. But there are 3 months in a quarter. 13 is not divisible by three so you end up putting the extra week into one of the months so that it's always consistent.<ul><li>5/4/4 means the 1st month of the quarter has the extra week. 4/5/4 means the 2nd month has the extra week, etc. In the 5-4-4 calendar, the 53rd week is added onto the last quarter of the year.</li><li>4-5-4:January has four weeks, February has five weeks, March has four weeks, and so on.</li><li>4-4-5: January has four weeks, February has four weeks, March has five weeks, and so on.</li><li>5-4-4: January has five weeks, February has four weeks, March has four weeks, and so on.</li></ul> |

>[!NOTE]
>These calendar options are supported across all Adobe Analytics tools (Analysis Workspace, Reports & Analytics, Report Builder, Activity Map), except for Data Warehouse. Data Warehouse fully supports only the Gregorian calendar. When choosing a non-Gregorian calendar, Data Warehouse will use the expected date range of the non-Gregorian calendar, however the day/week/month breakdowns within the rows of the report may not be what is expected from a non-Gregorian calendar.
