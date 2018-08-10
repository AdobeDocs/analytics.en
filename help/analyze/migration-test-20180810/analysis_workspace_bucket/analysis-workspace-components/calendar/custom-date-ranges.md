---
title: Create custom date ranges
description: Create custom date ranges in Analysis Workspace, and save them as Time components.
keywords: Analysis Workspace
seo-description: Create custom date ranges in Analysis Workspace, and save them as Time components.
seo-title: Create custom date ranges
solution: Analytics
topic: Reports and analytics
uuid: b7201df6-ea65-42d0-b480-f8a5e7effb51
index: y
internal: n
snippet: y
translate: y
---

# Create custom date ranges

**[!UICONTROL Components]** > **[!UICONTROL New Date Range]** 

A date range applies at the panel level. To add a date range to your project, click **[!UICONTROL Panels > Select Panel]** and specify a new date range. 

+ [ Date Range for "Two Months Ago" ](custom-date-ranges.md#section_C4109C57CB444BB2A79CC8082BD67294)
+ [ 7-Day Rolling Date Range ](custom-date-ranges.md#section_7EF63B2E9FF54D2E9144C4F76956A8DD)

## Date range for "two months ago" {#section_C4109C57CB444BB2A79CC8082BD67294}

The following custom date range shows a date range for "two months ago," with a Summary Change visualization showing directional change. 

![](graphics/date-range-two-months-ago.png) 

The custom date range is displayed at the top of the [!UICONTROL Date Range] component panel in your project: 

![](graphics/date-range-panel-two-months-ago.png) 

You can drag this custom date range into a column alongside a custom, monthly rolling date range using the Last Month preset for a comparison. Add a Summary Change visualization and select the totals from each column to show directional change: 

![](graphics/date-range-two-months-table.png) 

## 7-day rolling date range {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

A date range applies to the panel level. To add a date range to your project, click **[!UICONTROL Actions > Add Panel]**, and specify a new date range. 

In the Date Range Builder, you can create a custom date range that displays in the Components panel with other date ranges. 

For example, you can create a date range that specifies a 7-day rolling window that ends one week ago: 

![](graphics/create_date_range.png) 

Use *`rolling daily`*. 

+ The Start settings would be *`current day minus 14 days`*. 
+ The End settings would be *`current day minus 7 days`*. 
+ This date range can be a component that you drag onto any freeform table. 
