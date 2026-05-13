---
description: The first step when creating a request in Report Builder.
title: Data requests - Request Wizard Step 1
feature: Report Builder
role: User, Admin
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
TQID: https://experienceleague.adobe.com/87MzdxBePRZKBttF3P6XhuDq5hR6XpEWaLdrYDMu-5Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Data requests - Request Wizard Step 1

{{legacy-arb}}

On the Request Wizard: Step 1 form, you select the report suite, report type, segments, and configure dates.

 ![Screenshot showing the Request Wizard: Step 1 form.](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**: The list of report suites available to you based on your login credentials. See [Select Report Suites](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Range Selector**: Lets you select a report suite ID from a cell in Excel. See [Select Report Suites](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Segment**: Segments are custom subsets of data, or data filtered by rules that you create. Segments are based on hits, visits, and visitors. See the [Analytics Segmentation Guide](/help/components/segmentation/seg-home.md) for more information about segments.

   For example, you can run a [!UICONTROL Pages Report], and then apply a First Time Visits segment.

1. **Allow Publishing List Override**: Publishing lists were a feature in Reports & Analytics, which has been [end-of-lifed](https://new.express.adobe.com/webpage/WFCyq7w8kijmB?).

1. **Report Type**: Specifies the base report you want to run in your data request. You run one report per request, and that report can have one-to-many dimensions and one-to-many metrics. Metrics and dimensions for a report type are displayed on the [!UICONTROL Request Wizard; Step 2] interface. See [Select Report Types](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md).

1. **Date Ranges**: Defines the time span covered by the request. Several types of request time periods are available, such as preset, fixed, and rolling. The maximum number of periods is 366. You can also choose a date range specified by a cell, and save date ranges as templates for later use.  See [Configuring Report Dates](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md) 

1. **Apply Granularity**: Specifies the level of time-based detail that is included in the report. See [Granularity](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md).

## Troubleshooting

Sometimes the request wizard appears off-screen, especially for users that move between monitor setups. For example, you use a docking station at work, and your laptop screen at home. If you click 'Create' again while a request wizard is already open, you get the following error:

"You first need to complete the request wizard process before starting a new one."

Moving the request wizard back on-screen resolves this issue.

1. Open Microsoft Excel and log in to Report Builder.
2. Click [!UICONTROL Create], which opens the request wizard off-screen.
3. Press `[Alt]` + `[Space]`.
4. Press `[M]`.
5. Press any of the arrow keys.
6. Move your mouse, which attaches the request wizard to your cursor
7. Click the mouse to release the request wizard on-screen.
