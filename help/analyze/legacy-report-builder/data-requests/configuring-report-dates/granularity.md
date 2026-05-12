---
description: On the Request Wizard  Step 1, you can apply a level of granularity to the data request. Granularity specifies the level of time-based detail that is included in the report.
title: Granularity
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
TQID: https://experienceleague.adobe.com/26j4Fernl4bfuYeyuVVzw1K5hZvNSD6pDUVOfEc0J8s
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
# Granularity

{{legacy-arb}}

On the Request Wizard: Step 1, you can apply a level of granularity to the data request. Granularity specifies the level of time-based detail that is included in the report.

Valid values are Hour, Day, Week, Month, Quarter, Year, and Aggregated.

## How Report Builder processes granularity

Suppose you choose a date range for a month with [!UICONTROL Month] granularity. Requests show totals for the metric based on exactly one month's worth of data. If the date range of your request spans one quarter, the report shows three figures: one for each month unit, or fraction thereof. If today is March 18, choosing the last quarter returns one figure for January 1 - January 31, another figure for February 1 - February 28, and a final figure for March 1 - March 17.
