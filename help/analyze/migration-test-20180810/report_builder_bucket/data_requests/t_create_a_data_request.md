---
description: Steps to create a basic data request.
seo-description: Steps to create a basic data request.
seo-title: Create a data request
solution: Analytics
title: Create a data request
topic: Report builder
uuid: 4684f1af-feed-45d1-9ac8-01af08991adf
index: y
internal: n
snippet: y
translate: y
---

# Create a data request


>1. In Excel, click ** [!UICONTROL  Create] **.
>1. In the [!UICONTROL  Request Wizard: Step 1] window, select a [ report suite ](t_select_report_suites.md#task_59444416F6F042D1998217AE91580913).
>1. (Optional) Select a segment to apply to the request. Once you have selected one or more segments, they will move to the top of the list.

>       [ Analytics Segmentation Guide ](https://marketing.adobe.com/resources/help/en_US/analytics/segment/)1. (Optional) Select a [ publishing list ](allow_publishing_list_overrides.md#concept_BCB19A20DC4B4B8D984F9670EE018D8C) to use for distribution.
>1. Select a [ report type ](select_report_types.md#concept_C711B27E6FB64C18AC564EE142FC7EFC).
>1. Specify a [ date range ](configuring_report_dates.md#concept_4419F6B0BC274DC7A07086DA56703DFE) and report [ granularity ](granularity.md#concept_A13CBA2962E24FF882456135431B7ADB).
>1. Click ** [!UICONTROL  Next] **.
>1. In the [ Layout - Request Wizard Step 2 ](layout.md#concept_D66E1C2217E24E1F837AC064C61919DB) window, specify a layout:

>   |  Element  | Description  |
>   |---|---|
>   |  Pivot Layout  | Provides a row, column, and metric grid for layout, similar to standard Excel tables. Using this layout, you can add breakdown requests within an original request.  |
>   |  Custom Layout  | Provides most of the functionality of the [!UICONTROL  Pivot Layout] but lets you choose where each item in the grid should be located in the spreadsheet. This layout provides the flexibility available in previous releases.  |

>
>1. On the [!UICONTROL  Metrics] tab, double-click (or drag) metrics in the tree to add them to the [!UICONTROL  Metrics] grid.
>1. On the [!UICONTROL  Dimensions] tab, double-click (or drag) dimensions to the [!UICONTROL  Row Labels] grid.
>   The [ dimensions ](http://marketing.adobe.com/resources/help/en_US/reference/index.html?f=dimensions) available in Step 2 depend on the base report you selected in Step 1, and on the configuration of your report suite. The dimensions are items that correlate, sub-relate, or are a classification of the original report type metric you selected on the [!UICONTROL  Request Wizard: Step 1] window. Adding more than one dimension in Step 2 is how you create a breakdown in your data request. 

>   See [ Add Metrics and Dimensions ](t_add_metrics_and_dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4) for more information. 
>
>1. Select an insertion location for the request (  ![](Graphics/select_cell_icon.png)).
>1. After selecting the cell, click the cell selector to return to the [ Request Wizard Step 2 ](request_wizard_step_2.md#concept_117A581D42B945CA9750F3059A9A9B39) window.
>1. Continue configuring layout settings as necessary. (See [ Configure the Layout ](layout.md#concept_D66E1C2217E24E1F837AC064C61919DB).)
>1. On the [!UICONTROL  Request Wizard: Step 2] window, click ** [!UICONTROL  Finish] ** to process the request.
>   If you modify a spreadsheet that already contains requests, but instead of clicking [!UICONTROL  Finish], you click [!UICONTROL  Cancel &amp;amp; Refresh], report builder refreshes the edited requests already mapped to the spreadsheet before closing the [!UICONTROL  Request Wizard].>
