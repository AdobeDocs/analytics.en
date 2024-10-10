---
description: Learn how to add, remove, or replace metrics in a pre-existing request or across a group of requests.
title: How to edit metrics across multiple requests
feature: Report Builder
role: User, Admin
exl-id: e537b67a-aa07-4acd-a476-7497426e2f7d
---
# Edit metrics across multiple requests

Add, remove, or replace metrics in a pre-existing request or across a group of requests.

## Add metrics {#section_3FBDA9668039404895059618D70FCBCD}

When you add metrics, consider the following guidelines:

* Metrics can be added only to Pivot Layout requests. 
  If some of the selected requests are Custom Layouts, metrics cannot be added. If the layout is customized, Report Builder does not know where in the spreadsheet to place the new metric.
* If you select only Custom Layout requests, the **[!UICONTROL Add Metrics]** option is not available.
* Adding metrics increases the size of a request and may cause it to overlap with another request. Make sure your request has enough space around it to allow for adding metrics.
* If the added metric is already present in one of the selected requests, it will not be added to that request.

To add one or more metrics

1. Select one or more requests in Excel and right-click to select **[!UICONTROL Edit Metrics]**. (Or, click **[!UICONTROL Manage]** > **[!UICONTROL Edit Multiple]** > `<choose metric>` > **[!UICONTROL Edit Group]** to select the group of requests to modify.)
1. Select **[!UICONTROL Add Metric(s)]**and select the metrics to add.

   ![Screenshot showing the Edit Request, Add Metrics(s) option selected.](assets/add_metric.png)

1. Refresh the request to see actual data. Offline data is shown until you refresh the data.

## Replace metrics 

When you replace metrics, consider the following guidelines:

* Only 1:1 substitutions are allowed. 1:many or many:1 are not allowed.
* If the selected metric is not present in one of the selected requests, the request is left unchanged.
* The new metric is placed in the same location as the substituted metric.

  * **In a Pivot Layout**, if a pivot layout request outputs date, visit, visitors, daily unique and *visitors* is replaced by *revenue*, the updated request layout will be: date, visit, revenue, and daily unique.
  * **In a Custom Layout**, if the *visitors* metric was output in cell F11, the updated request layout will show *revenue* in the same cell F11.

* If the substituted metric had some operation applied to it (average, pre-pended text, post-pended text, microcharting), these operations will also be applied to the new metric.

To replace a metric

1. Select one or more requests in Excel and right-click to select **[!UICONTROL Edit Metrics]**. Alternatively, you can click **[!UICONTROL Manage]** > **[!UICONTROL Edit Multiple]** > **`<choose metric>`** > **[!UICONTROL Edit Group]** to select the group of requests to modify.

1. Select **[!UICONTROL Replace Metric]**.

   ![Screenshot of the Edit Group screen with Replace Metric selected.](assets/replace_metric.png)

1. Select the metric you want to replace and the replacement metric.
1. Refresh the request. Offline data is shown until you refresh the data.

## Remove metrics {#section_D3CD5BAC7670416593B633B2B8423C60}

When you remove metrics, consider the following guidelines:

* If any of the metrics that you select for removal are not present in one of the selected requests, the request is left unchanged.
* In a pivot layout, removing a metric causes the layout to shift for metrics that are located after the removed metric. For example, if a pivot layout request outputs date, visits, visitors, and daily unique, and you remove *visits*, the updated layout for the request will show: date, visitors, and daily unique.

To remove metrics

1. Select one or more requests in Excel and right-click to select **[!UICONTROL Edit Metrics]**. Alternatively, click **[!UICONTROL Manage]** > **[!UICONTROL Edit Multiple]** > **`<choose metric>`** > **[!UICONTROL Edit Group]** to select the group of requests to modify.

1. Select **[!UICONTROL Remove Metric(s)]**.

   ![Screenshot showing the Edit Group and Remove Metric(s) option selected.](assets/remove_metric.png)

1. Select one or more metrics to remove from the request.
1. Refresh the request. Until you refresh, you will see offline data.
