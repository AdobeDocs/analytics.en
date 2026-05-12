---
description: Two important considerations when using the Customize Expression to set the date range
title: Customized Date Considerations
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
feature: Report Builder
role: User, Admin
exl-id: 66b817b3-7e9e-4030-92f3-797e730f9661
TQID: https://experienceleague.adobe.com/7PLNffmZnNnQ2X0HgnqYa8R3zWQvFPMSM8sbWocmxH4
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
---
# Customized Date Considerations

{{legacy-arb}}

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

In Europe and some other countries, the week begins on Monday, rather than Sunday. In this case, you can customize the calendar to change the start date. (See [Custom Calendar](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md).)
