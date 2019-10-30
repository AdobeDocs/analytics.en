---
description: Two important considerations when using the Customize Expression to set the date range 
seo-description: Two important considerations when using the Customize Expression to set the date range 
seo-title: Considerations
solution: Analytics
title: Customized Date Considerations
topic: Report builder
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
---

# Customized Date Considerations

Two important considerations when using the Customize Expression to set the date range:

* The day the report (As Of) is run (or requests refreshed) determines what data is available.
* The rollover of start and end dates of the report affects the date range covered by the report.

Because the availability of data is sensitive both to the time frame of the report and the date that you refresh requests in the report, ensure that you run the report on the appropriate day to extract the desired information. The examples below demonstrate both of these considerations.

Assume you make a request for [!UICONTROL Page Views] using Aggregated granularity. In North America, the week begins on Sunday. To obtain updated reports for the period Sunday to Saturday (for example, November 23 to November 29, 2008), run the report (refresh requests) on Sunday (November 30) for the previous week (11/23 to 11/29).

Use this customized expression:

*From:* cw-1w *To:* cw-1d

An analysis of the customize expression when the inclusive [!UICONTROL End Date] for the request is 11/30:

*From:* cw-1w

the day of the current week starting on Sunday, November 30 minus seven days = the day of the past week starting on Sunday, November 23

*To:* cw-1d

the day of the current week starting on Sunday, November 30 minus one day = Saturday, November 29

After the customized expression is mapped to the spreadsheet, refresh the request using Sunday, November 30, 2008 as the inclusive [!UICONTROL End Date] for the floating request. The data will reflect the week-long period.

If instead you refresh the expression and specify Saturday, November 29 as the [!UICONTROL End Date] for the floating request, the data will reflect the week 11/16 to 11/22. This is because the reference date for the request refresh is one day earlier.

Here are the differences when the inclusive [!UICONTROL End Date] for the request is 11/29:

*From:* cw-1w

the day of the current week starting on Sunday, November 23 minus seven days = the day of the past week starting on Sunday, November 16

*To:* cw-1d

the day of the current week starting on Sunday, November 23 minus one day = Saturday, November 22

In Europe and some other countries, the week begins on Monday, rather than Sunday. In this case, you can customize the calendar to change the start date. (See [Custom Calendar](../../../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md#concept_4342A844600048759EEDABD164AC3F5A).) 
