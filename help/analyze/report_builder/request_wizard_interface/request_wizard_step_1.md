---
description: On the Request Wizard  Step 1 form, you select the report suite, report type, segments, and configure dates.
seo-description: On the Request Wizard  Step 1 form, you select the report suite, report type, segments, and configure dates.
seo-title: Request Wizard Step 1
solution: Analytics
title: Request Wizard Step 1
topic: Report builder
uuid: 8d163c0c-14ad-4626-9cc5-f2c76dc80bf0
index: y
internal: n
snippet: y
---

# Request Wizard Step 1

On the Request Wizard: Step 1 form, you select the report suite, report type, segments, and configure dates.

 ![](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**: The list of report suites available to you based on your login credentials. See [Select Report Suites](../../report_builder/data_requests/selecting_report_suites/t_select_report_suites.md#task_59444416F6F042D1998217AE91580913). 

1. **Range Selector**: Lets you select a report suite ID from a cell in Excel. See [Select Report Suites](../../report_builder/data_requests/selecting_report_suites/t_select_report_suites.md#task_59444416F6F042D1998217AE91580913). 

1. **Segment**: Segments are custom subsets of data, or data filtered by rules that you create. Segments are based on hits, visits, and visitors. See the [Analytics Segmentation Guide](https://marketing.adobe.com/resources/help/en_US/analytics/segment/) for more information about segments.

   For example, you can run a [!UICONTROL Pages Report], and then apply a First Time Visits segment. 

1. **Allow Publishing List Override**: When you schedule a report, you can choose a publishing list to use for distribution. Publishing lists are set up in **[!UICONTROL Analytics]** > **[!UICONTROL Admin tools]**. The report suite for this request is replaced by the report suite ID assigned to each recipient in the publishing list. See [Allow Publishing List Overrides](../../report_builder/data_requests/allow_publishing_list_overrides.md#concept_BCB19A20DC4B4B8D984F9670EE018D8C). 

1. **Report Type**: Specifies the base report you want to run in your data request. You run one report per request, and that report can have one-to-many dimensions and one-to-many metrics. Metrics and dimensions for a report type are displayed on the [!UICONTROL Request Wizard; Step 2] interface. See [Select Report Types](../../report_builder/data_requests/c_report_types/select_report_types.md#concept_C711B27E6FB64C18AC564EE142FC7EFC). 

1. **Date Ranges**: Defines the time span covered by the request. Several types of request time periods are available, such as preset, fixed, and rolling. The maximum number of periods is 366. You can also choose a date range specified by a cell, and save date ranges as templates for later use.  See [Configuring Report Dates](../../report_builder/data_requests/configuring_report_dates/configuring_report_dates.md#concept_4419F6B0BC274DC7A07086DA56703DFE) 

1. **Apply Granularity**: Specifies the level of time-based detail that is included in the report. See [Granularity](../../report_builder/data_requests/configuring_report_dates/granularity.md#concept_A13CBA2962E24FF882456135431B7ADB).

>[!MORE_LIKE_THIS]
>
>* [Create a Data Request](t_create_a_data_request.md#task_65B453C8F015429A8EA73A1B64025B6C)
