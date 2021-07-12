---
description: The first step when creating a request in Report Builder.
title: Data requests - Request Wizard Step 1
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
role: User, Admin
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
---
# Data requests - Request Wizard Step 1

On the Request Wizard: Step 1 form, you select the report suite, report type, segments, and configure dates.

 ![](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**: The list of report suites available to you based on your login credentials. See [Select Report Suites](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Range Selector**: Lets you select a report suite ID from a cell in Excel. See [Select Report Suites](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Segment**: Segments are custom subsets of data, or data filtered by rules that you create. Segments are based on hits, visits, and visitors. See the [Analytics Segmentation Guide](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html) for more information about segments.

   For example, you can run a [!UICONTROL Pages Report], and then apply a First Time Visits segment.

1. **Allow Publishing List Override**: When you schedule a report, you can choose a publishing list to use for distribution. Publishing lists are set up in **[!UICONTROL Analytics]** > **[!UICONTROL Admin tools]**. The report suite for this request is replaced by the report suite ID assigned to each recipient in the publishing list. See [Allow Publishing List Overrides](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md).

1. **Report Type**: Specifies the base report you want to run in your data request. You run one report per request, and that report can have one-to-many dimensions and one-to-many metrics. Metrics and dimensions for a report type are displayed on the [!UICONTROL Request Wizard; Step 2] interface. See [Select Report Types](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).

1. **Date Ranges**: Defines the time span covered by the request. Several types of request time periods are available, such as preset, fixed, and rolling. The maximum number of periods is 366. You can also choose a date range specified by a cell, and save date ranges as templates for later use.  See [Configuring Report Dates](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) 

1. **Apply Granularity**: Specifies the level of time-based detail that is included in the report. See [Granularity](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).

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
