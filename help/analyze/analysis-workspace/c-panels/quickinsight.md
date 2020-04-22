---
description: null
title: Quick Insights Builder
---

# Quick Insights Builder

>[!IMPORTANT]
>
>Quick Insights is currently in beta testing and not generally available to all Adobe Analytics customers yet.

Quick Insights provides guidance for non-analysts and new users of Analysis Workspace to learn how to answer business questions quickly and easily. It is also a great tool for advanced users who want to answer a simply question quickly without having to build a table themselves.

When you first start using this Analysis Workspace, you might wonder what visualizations would be most useful, which dimensions and metrics might facilitate insights, where to drag and drop items, where to create a segment, etc. 

To help with this, based on your own company's usage of data components in Analysis Workspace, Quick Insights leverages an algorithm that will present you with the most popular dimensions, metrics, segments, and date ranges your company uses. 

Quick Insights helps you

* Properly build a data table and accompanying visualization in Analysis Workspace.
* Learn the terminology and vocabulary for basic components and pieces of Analysis Workspace.
* Do simple breakdowns of dimensions, add multiple metrics, or compare segments easily within a Freeform table.
* Change or try out various visualization types to find the find tool for your analysis quickly and intuitively.

## Basic key terminology

Following are some of the basic terms you need to be familiar with. Each data table consists of 2 or more building blocks that you utilize to tell your data story.

|Building block|Definition|
|---|---|
|Dimension|Dimensions are descriptions or characteristics of metric data that can be viewed, broken down, and compared in a project. They are non-numeric values and dates that break down into dimension items. For example, "browser", or "page" are dimensions.|
|Dimension item|Dimension items are individual values for a dimension. For example, dimension items for the browser dimension would be "Chrome", "Firefox", "Edge", etc.|
|Metric|Metrics are quantitative information about visitor activity, such as views, click-throughs, reloads, average time spent, units, orders, revenue, and so on.|
|Visualization|Workspace offers [a number of visualizations](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) to build visual representations of your data.|
|Segment|Segments let you identify subsets of visitors based on characteristics or website interactions. For example, you can build Visitor segments based on attributes: browser type, device, number of visits, country, gender, or based on interactions: campaigns, keyword search, search engine, or based on exits and entries: visitors from Facebook, a defined landing page, referring domain, or based on custom variables: form field, defined categories, customer ID.  |

## Get started with Quick Insights

1. Log in to Adobe Analytics using the credentials you have been provided with.
1. Go to [!UICONTROL Workspace] and click **[!UICONTROL Create New Project]** and then click **[!UICONTROL Quick Insights Builder]**.

    ![](assets/qibuilder.png)

1. When you first start out, go through the short tutorial that teaches you some of the Quick Insight Builder basics. Or, click to **[!UICONTROL Skip Tutorial]**.
1. Select your building blocks (also known as components): dimensions (orange), metrics (green), segments (blue), or date ranges (purple) You have to select at least one dimension and one metric for a table to be built automatically. 

    ![](assets/qibuilder2.png)

    You have three ways of selecting the building blocks:
    * Drag and drop them from the left rail
    * If you know what you are looking for: Start typing the name and Quick Insights will fill in the blanks for you
    * Click on the drop-down and search the list

1. When you have added at least one dimension and one metric, the following will be created for you:

    * A Freeform table with the dimension on the left (vertical) and the metric(s) at the top (horizontal). Check out this table: 

1. (Optional) Drill down on dimensions and see dimension items by clicking the > right-arrow next to the dimension.



## Known limitations

If you try to edit directly within the table, it will cause the Quick Insight builder (the fill-in-the-blank tool) to become out of sync. You can restore it to the previous Quick Insight settings, but if not, building directly will cause the table to now behave as a traditional Freeform table.

