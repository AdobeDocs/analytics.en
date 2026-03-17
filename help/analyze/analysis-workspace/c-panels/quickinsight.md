---
description: Understand how to use the Quick insights panel to guide you in building freeform tables and visualizations in Analysis Workspace.
title: Quick Insights Panel
feature: Panels
role: User, Admin
exl-id: 29b26ec9-d410-43d6-a317-ca7587f5dd31
---
# Quick insights panel {#quick-insights-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_quickinsights_button"
>title="Quick insights"
>abstract="Create a panel to quickly build a freeform table and accompanying visualization to analyze and uncover insights faster."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_This article documents the Quick insights panel in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_See [Quick insights panel](/help/analyze/analysis-workspace/c-panels/quickinsight.md) for the_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** version of this article._

>[!ENDSHADEBOX]


[!UICONTROL Quick Insights] provides guidance for non-analysts and new users of [!UICONTROL Analysis Workspace] to learn how to answer business questions quickly and easily. It is also a great tool for advanced users who want to answer a simple question quickly without having to build a table themselves.

When you first start using this [!UICONTROL Analysis Workspace], you might wonder:

* what visualizations would be most useful, 
* which dimensions and metrics might facilitate insights, 
* where to drag and drop items, 
* where to create a filter, 
* and more. 

To help with these questions, [!UICONTROL Quick insights] leverages an algorithm that presents you with the most popular dimensions, metrics, segments, and date ranges your company uses. This algorithm is based on your own company's usage of data components in [!UICONTROL Analysis Workspace]. In fact, you see dimensions, metrics, and segments tagged with [!UICONTROL POPULAR] in the drop-down list, as shown here:

![The Quick Insights panel.](assets/popular-tag.png)

[!UICONTROL Quick Insights] helps you

* Properly build a data table and an accompanying visualization in [!UICONTROL Analysis Workspace].
* Learn the terminology and vocabulary for basic components and pieces of [!UICONTROL Analysis Workspace].
* Do simple breakdowns of dimensions, add multiple metrics, or compare segments easily within a [!UICONTROL Freeform table].
* Change or try out various visualization types to find the find tool for your analysis quickly and intuitively.

## Basic key terminology

The following are some of the basic terms that you need to be familiar with. Each data table consists of 2 or more building blocks (components) that you use to tell your data story.

|Building block (Component)|Definition|
|---|---|
|**[!UICONTROL Dimension]** |Dimensions are descriptions or characteristics of metric data that can be viewed, broken down, and compared in a project. They are non-numeric values and dates that break down into dimension items. For example, *browser* or *page* is a dimension.|
|**[!UICONTROL Dimension item]** |Dimension items are individual values for a dimension. For example, dimension items for the browser dimension would be *Chrome*, *Firefox*, *Edge*, or others.|
|**[!UICONTROL Metric]** |Metrics are quantitative information about visitor activity, such as views, click-throughs, reloads, average time spent, units, orders, revenue, and so on.|
|**[!UICONTROL Visualization]**|Workspace offers [a number of visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) to build visual representations of your data. Such as bar charts, donut charts, histograms, line charts, maps, scatterplots, and others.|
|**[!UICONTROL Dimension Breakdown]**|A dimension breakdown is a way to break down a dimension by other dimensions. For example, you could break down the US States by Mobile Devices to get the mobile device visits per state. Or you could break Mobile Devices down by Mobile Device types, by Regions, by Internal Campaigns, and more.|
|**[!UICONTROL Segments]**| Segments let you identify subsets of visitors based on characteristics or website interactions. For example, you can build [!UICONTROL Visitor] segments based on <li>attributes: browser type, device, number of visits, country, gender, or</li><li>interactions: campaigns, keyword search, search engine, or</li><li>exits and entries: visitors from Facebook, a defined landing page, referring domain, or</li><li> custom variables: form field, defined categories, customer ID.  |

## Use

To use a **[!UICONTROL Quick insights]** panel:

1. Create a **[!UICONTROL Quick insights]** panel. For information about how to create a panel, see [Create a panel](panels.md#create-a-panel).

1. When you first use a **[!UICONTROL Quick insights]** panel, you might want to go through the short [!UICONTROL Intro tutorial] that teaches you some of the basics. Select ![HelpOutline](/help/assets/icons/HelpOutline.svg) next to the Quick insights panel title and select **[!UICONTROL Intro tutorial]** from the popup. 

1. Specify the [input](#panel-input) for the panel.

1. Observe the [output](#panel-output) for the panel.


### Panel input

Select your building blocks: 

* **[!UICONTROL Analyze]** - specify a dimension (orange)
* **[!UICONTROL by]** - specify a metric (green)
* **[!UICONTROL filter by]** - specify a segment (blue)
* **[!UICONTROL on]** - specify a date range (purple).

You have to select at least one dimension and one metric for the visualization to function properly.



You can specify the building blocks in three ways:

* Drag and drop components from the left panel.
* Start typing in one of the building block fields. When input is found, the building block field auto populates with possible values.
* Specify a building block drop-down (for example **[!UICONTROL Country]** in **[!UICONTROL Analyze]**) and search the list of possible value (using ![ChevronRight](/help/assets/icons/ChevronRight.svg)) for the value you want to use (for example, **[!UICONTROL Country code]**).

Select **[!UICONTROL Clear]** to clear all input fields.


### Panel output

1. When you have added at least one dimension and one metric, you can see the results.
   
   ![The Freeform table showing the dimension vertically and the metric horizontally.](assets/quick-insights-output.png)

    * A Freeform table with the dimension ([!UICONTROL Country Site]) and metric ([!UICONTROL Visits]), segmented by [!UICONTROL Visits] from [!UICONTROL Search Engines] for the [!UICONTROL Last 12 months].

    * An accompanying visualization, in this case a [bar chart](/help/analyze/analysis-workspace/visualizations/bar.md). The visualization that is generated is based on the type of data you added to the table. Any time-based data (such as [!UICONTROL Visits] per Day/Month) defaults to a [!UICONTROL Line] chart. Any non-time-based data (such as [!UICONTROL Visits] per [!UICONTROL Device]) defaults to a [!UICONTROL Bar] chart. You can change the type of visualization by clicking on the drop-down arrow next to the visualization type.

1. Try adding some more refinements as described below under [More tips](#more-tips)

1. You might want to save your project, using **[!UICONTROL Project > Save]**.

## More tips

Other useful hints pop up in the [!UICONTROL Quick Insights Builder], some of them depending on your last action.

* First, you might want to complete the **[!UICONTROL More tips]** tutorial. This tutorial shows up 24 hours after you have created a project with at least one dimension and one metric. Select ![HelpOutline](/help/assets/icons/HelpOutline.svg) next to the Quick insights panel title and select **[!UICONTROL More tips]** from the popup. 

    ![The Quick Insights Panel notification displayed after you select the Help icon.](assets/qibuilder4.png)

* You can analyze multiple dimensions and metrics, combine or compare segments, and specify a date range:

  ![Quick Insights Builder Result](assets/qibuilder-result.png)

  * **[!UICONTROL Analyze]** dimension **[!UICONTROL Broken-Down by]**: You can use up to 3 levels of breakdowns on dimensions to drill down to the data you really need. See ➊, ➋, and ➌.

  * Add more metrics **[!UICONTROL by]**: You can add up to 2 more metrics. See ➍ and ➎.

  * **[!UICONTROL filter by]**: You can add up to 2 more segments. For example, add Bookings as a segment and combine that segment with Frequent Bookers and First Time Fliers segments you compare. See ➏, ➐, and ➑.

  * on: You can specify the date range. See ➒.

## Known limitations

If you try to edit directly within the table, the [!UICONTROL Quick Insights] panel can become out of sync. Select **[!UICONTROL Resync Builder]** at the top right of the panel to restore it to the previous [!UICONTROL Quick Insights] settings.

You get a warning before adding anything directly to the table:

 ![The Resync Builder option warning.](assets/qibuilder-outofsync.png)

Otherwise, building directly causes the table to behave as a traditional Freeform table, without the helpful features for new users.


>[!MORELIKETHIS]
>
>[Create a panel](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>
<!--
# Quick Insights panel

[!UICONTROL Quick Insights] provides guidance for non-analysts and new users of [!UICONTROL Analysis Workspace] to learn how to answer business questions quickly and easily. It is also a great tool for advanced users who want to answer a simple question quickly without having to build a table themselves.

When you first start using this [!UICONTROL Analysis Workspace], you might wonder what visualizations would be most useful, which dimensions and metrics might facilitate insights, where to drag and drop items, where to create a segment, etc. 

To help with this, and based on your own company's usage of data components in [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] leverages an algorithm that will present you with the most popular dimensions, metrics, segments, and date ranges your company uses. In fact, you will see dimensions, metrics, and segments tagged as [!UICONTROL Popular] in the drop-down list, as shown here:

![](assets/popular-tag.png)

[!UICONTROL Quick Insights] helps you

* Properly build a data table and an accompanying visualization in [!UICONTROL Analysis Workspace].
* Learn the terminology and vocabulary for basic components and pieces of [!UICONTROL Analysis Workspace].
* Do simple breakdowns of dimensions, add multiple metrics, or compare segments easily within a [!UICONTROL Freeform table].
* Change or try out various visualization types to find the find tool for your analysis quickly and intuitively.

Here is a video overview of the [!UICONTROL Quick Insights] panel:

>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/using-panels/quick-insights-panel-in-analysis-workspace)

## Basic key terminology

Following are some of the basic terms you need to be familiar with. Each data table consists of 2 or more building blocks (components) that you utilize to tell your data story.

|Building block (Component)|Definition|
|---|---|
|[!UICONTROL Dimension]|Dimensions are descriptions or characteristics of metric data that can be viewed, broken down, and compared in a project. They are non-numeric values and dates that break down into dimension items. For example, "browser", or "page" are dimensions.|
|[!UICONTROL Dimension item]|Dimension items are individual values for a dimension. For example, dimension items for the browser dimension would be "Chrome", "Firefox", "Edge", etc.|
|[!UICONTROL Metric]|Metrics are quantitative information about visitor activity, such as views, click-throughs, reloads, average time spent, units, orders, revenue, and so on.|
|[!UICONTROL Visualization]|Workspace offers [a number of visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) to build visual representations of your data, such as bar charts, donut charts, histograms, line charts, maps, scatterplots, and others.|
|[!UICONTROL Dimension Breakdown]|A dimension breakdown is a way to literally break down a dimension by other dimensions. In our example, you could break down US States by Mobile Devices to get the mobile device visits per state, or you could break Mobile Devices down by Mobile Device types, by Regions, by Internal Campaigns, etc..|
|[!UICONTROL Segment]|Segments let you identify subsets of visitors based on characteristics or website interactions. For example, you can build [!UICONTROL Visitor] segments based on attributes: browser type, device, number of visits, country, gender, or based on interactions: campaigns, keyword search, search engine, or based on exits and entries: visitors from Facebook, a defined landing page, referring domain, or based on custom variables: form field, defined categories, customer ID.  |

## Get started with Quick Insights

1. Log in to Adobe Analytics using the credentials you have been provided with.
1. Go to [!UICONTROL Workspace] and click **[!UICONTROL Create New Project]** and then click **[!UICONTROL Quick Insights]**. (You can also access this panel from the **[!UICONTROL Panel]** menu in the left rail.)

    ![](assets/qibuilder.png)

    ![](assets/qi-panel.png)

1. When you first start out, go through the short tutorial that teaches you some of the [!UICONTROL Quick Insights panel] basics. Or, click to **[!UICONTROL Skip Tutorial]**.
1. Select your building blocks (also known as components): dimensions (orange), metrics (green), segments (blue), or date ranges (purple) You have to select at least one dimension and one metric for a table to be built automatically. 

    ![](assets/qibuilder2.png)

    You have three ways of selecting the building blocks:
    * Drag and drop them from the left rail.
    * If you know what you are looking for: Start typing and [!UICONTROL Quick Insights] will fill in the blanks for you.
    * Click on the drop-down and search the list.

1. When you have added at least one dimension and one metric, the following will be created for you:

    * A Freeform table with the dimension (here, US States) vertically and the metric (here, Visits) horizontally at the top. Check out this table: 

    ![](assets/qibuilder3.png)

    * An accompanying visualization, in this case a [bar chart](/help/analyze/analysis-workspace/visualizations/bar.md). The visualization that is generated is based on the type of data you added to the table. Any time-based data (such as [!UICONTROL Visits] per Day/Month) defaults to a [!UICONTROL Line] chart. Any non-time-based data (such as [!UICONTROL Visits] per [!UICONTROL Device]) defaults to a [!UICONTROL Bar] chart. You can change the type of visualization by clicking on the drop-down arrow next to the visualization type.

1. (Optional) Drill down on dimensions and see dimension items by clicking the > right-arrow next to the dimension.

1. Try adding some more refinements as described below under "More tips."

1. Save your project by clicking **[!UICONTROL Project > Save]**.

## More tips

Other useful hints will pop up in the [!UICONTROL Quick Insights Builder], some of them depending on your last action.

* First, complete the **[!UICONTROL More tips]** tutorial: Access it via the Help (?) icon next to the [!UICONTROL Quick Insights] title. This tutorial shows up 24 hours after you have created a project with at least one dimension and one metric.

    ![](assets/qibuilder4.png)

* **Breakdown by**: You can use up to 3 levels of breakdowns on dimensions to drill down to the data you really need.

    ![](assets/qibuilder5.png)

* **Add more metrics**: You can add up to 2 more metrics by using the AND operator to add them the table.

    ![](assets/qibuilder6.png)

* **Add more segments**: You can add up to 2 more segments by using the AND or OR operators to add them the table. Look at what happens to the table when you add Mobile Users OR Loyal Visitors. They are next to each other, above the metrics. If you added Mobile Users AND Loyal Visitors, you would see results from both segments together, and they would be stacked on top of each other in the table.

    ![](assets/qibuilder7.png)

## Known limitations

If you try to edit directly within the table, it will cause the [!UICONTROL Quick Insights] panel to become out of sync. You can restore it to the previous [!UICONTROL Quick Insights] settings by clicking **[!UICONTROL Resync Builder]** at the top right of the panel.

 ![](assets/qibuilder9.png)

You will get a warning before adding anything directly to the table:

 ![](assets/qibuilder8.png)

Otherwise, building directly will cause the table to now behave as a traditional Freeform table, without the helpful features for new users.

-->