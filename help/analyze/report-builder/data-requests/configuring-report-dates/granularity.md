---
description: On the Request Wizard  Step 1, you can apply a level of granularity to the data request. Granularity specifies the level of time-based detail that is included in the report.
title: Granularity
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
---
# Granularity

On the Request Wizard: Step 1, you can apply a level of granularity to the data request. Granularity specifies the level of time-based detail that is included in the report.

Valid values are Hour, Day, Week, Month, Quarter, Year, and Aggregated.

## How Report Builder processes granularity

Suppose you choose a date range for a month with [!UICONTROL Month] granularity. Requests show totals for the metric based on exactly one month's worth of data. If the date range of your request spans one quarter, the report shows three figures: one for each month unit, or fraction thereof. If today is March 18, choosing the last quarter returns one figure for January 1 - January 31, another figure for February 1 - February 28, and a final figure for March 1 - March 17.
