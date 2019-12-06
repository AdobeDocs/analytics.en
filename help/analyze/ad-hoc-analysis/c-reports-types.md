---
description: Descriptions of report types used in Experience Cloud.
title: Report types
topic: Ad hoc analysis
uuid: 357102eb-a172-40ec-a302-01c87abaacb5
---

# Report types

Descriptions of report types used in Experience Cloud.

## Ranked Reports {#concept_E1710FFFBB334F3D9DB63A1626DBCB01}

Displays a table with ranked items, using numbers and percentages in metrics. For example, a [!UICONTROL Pages Report] ranks the pages on your site based on traffic, and the detail table shows percentages and numbers for metrics like Page Views and Revenue. A horizontal bar chart is the default graph type. Graphs display a color for each metric. Ranked reports can display multiple metrics in a report.

<!-- 

c_reports_ranked.xml

 -->

Ranked graphs default to five items, but you can graph up to thirty items in the chart options.

## Trended Reports {#concept_65FEA92704024232BB21A5952939711F}

Lets you examine how conversions and events trend over a selected time granularity (Hour, Day, Week, Month, Quarter, or Year) during a reporting period.

<!-- 

c_reports_trended.xml

 -->

In the graph, the vertical axis displays the tracked items. The horizontal axis displays the time granularity. In the table, you can trend from a specific cell, and launch a full report from the cell. The date or time used is based on the cell's value.

You can also select multiple cells and launch a trended report, based on a selected granularity. When you trend from multiple cells, the report columns display data for the entire reporting period.

A [!UICONTROL Products Report] is an example of a trended report. You can see how much revenue a product made during the selected period. If your reporting period is a week, you can see how much revenue that product generated for each day of the time period, you can show a trend graph for a specific product on that day, or open a separate trended report for the selection.

## Trend from Cells {#task_AD9275BED5CE4D61AC25778D144406A4}

Steps describing how to launch a trend report from one or more cells in a table.

<!-- 

t_trend_row.xml

 -->

**To trend from cells** 

1. Open a ranked report.
1. In the table, locate the cell and click **[!UICONTROL Trend]**.

   ![](assets/TrendInspector_Buttcon.png)

1. To view a full report from the cell, click **[!UICONTROL Launch Trend Report]**.

   Alternatively, right-click the cell, then click **[!UICONTROL Trend Cell]**. You can also perform this task after selecting multiple cells.

## Totals Report {#concept_48E23FB3BCCD43DFB486A048960800A8}

<!-- 

c_reports_totals.xml

 -->

An executive-level report that shows bottom-line figures. It contains data for total revenue, page views, and orders. You can segment the report and add additional metrics to view additional data.

## Flow Reports {#concept_3E417D018F1B4566973F694B01E6439F}

Flow reports show the most common paths users take across pages, site sections, and servers.

<!-- 

c_reports_flow.xml

 -->

**Next Flow**

The [!UICONTROL Next Flow] report group has three reports: [!UICONTROL Next Page Flow], [!UICONTROL Next Section Flow], and [!UICONTROL Next Server Flow]. The reports in this group show you the most common pages, site sections, and servers that a visitor accessed after accessing the page, site section, or server you specify. These reports show you the most common paths taken through your website.

**Previous Flow**

Previous Flow reports are similar to Next Flow reports, except rather than seeing where visitors went after a selected page, you see where visitors were before visiting a specified page. The controls for using the report are identical to the controls for the Next Flow reports.

## Next Pages Flow {#concept_F7565234927942BEAF75D5D94A7AB47D}

Displays path views, or the number of times and percentages that a page was viewed within the constraints of the paths. For example, a Privacy Policy page might have 10,000 total page views, but only 500 of those page views occurred immediately before a Home Page. In this case, you would see 500 path views. You can view the report at the visit or visitor level. Percentages for each page are displayed beside the name of the page. The width of a line connected to a page depicts the relative percentage of visits.

<!-- 

c_reports_next_page_flow.xml

 -->

By default, this report displays the top 10 pages that users went to following the page you select. You can click on any underlined page to further expand the graph. There is no limit to the number of pages you can have on the graph, and you can hover over a page to see visit and revenue data for the page.

Use this report to:

* Understand what steps are taken most frequently after viewing a selected page.
* Optimize your site path design to funnel your traffic to a desired goal page.
* Identify where visitors are going instead of your desired goal pages.

## Next Server Flow {#concept_DB8C20E18AEA4051903C47A16C0E9C4E}

Displays the navigation data between servers on your site. When you select a server name from your site, the report shows you the number of visitors who navigated from that server to each of the other servers on your site within a single visit or across visits.

<!-- 

c_reports_next_server_flow.xml

 -->

For example, if you have specific data on different servers or have mirrored data on separate servers, the report shows you the path between servers that the users hit. This is also true of domains within your website. For example, you can see how many users went from a `https://www.mysite.com` to `https://info.mysite.com` or `https://sales.mysite.com`.

## Next Section Flow {#concept_7C9C8567E7DF477DA186E47DD3FD47A4}

The [!UICONTROL Next Section Flow] report is similar to the [!UICONTROL Next Page Flow] report. It displays data for Site Sections (groups of related web pages). If a page is contained in more than one site section, the report displays data for all site sections.

<!-- 

c_reports_next_section_flow.xml

 -->

For example, an online retailer might have site sections for its products and site sections for product brands. In this case, a product web page can fall under multiple sight sections. Though a product page has only been viewed once, the [!UICONTROL Next Section Flow] report shows a page view for each sight section associated with the page.

## Previous Page Flow {#concept_ADEAEBAE3F37401B977A27E03B5A523B}

Similar to the [!UICONTROL Next Page Flow] report. The [!UICONTROL Previous Page Flow] report displays multiple levels of the most popular pages that your visitors view before the selected page. The report also highlights pages from which visitors enter your site.

<!-- 

c_reports_previous_page_flow.xml

 -->

Use this report to:

* Understand what steps are taken most frequently before viewing a selected page.
* Optimize your site path design to funnel your traffic to a desired goal page.

## Previous Section Flow {#concept_30688D97B48449E1958866BAF376FA8C}

The [!UICONTROL Previous Section Flow] report is similar to the [!UICONTROL Previous Page Flow] report. It displays data for Site Sections (groups of related web pages). If a page is contained in more than one site section, then the report displays data for all site sections.

<!-- 

c_reports_previous_section_flow.xml

 -->

For example, an online retailer might have site sections for its products and site sections for product brands. In this case, a product web page can fall under multiple sight sections. Though a product page has only been viewed once, the [!UICONTROL Previous Section Flow] report shows a page view for each sight section associated with the page.

## Previous Server Flow {#concept_8E43208CAF2C4C358F19D4669B73822F}

This report shows you navigation data between servers on your site. When you select a server name from your site, the report shows you the number of visitors who navigated to that server from each of the other servers on your site within a single visit or across visits.

<!-- 

c_reports_previous_server_flow.xml

 -->

For example, if you have specific data on different servers or have mirrored data on separate servers, the report shows you the path between servers that the users hit. This is also true of domains within your website. For example, you can see how many users went from a `www.mysite.com` to `info.mysite.com` or `sales.mysite.com`.

## Conversion Funnel Reports {#concept_35A2EB61E84441CBB670C2E02CA26F81}

Conversion Funnel reports show conversion percentages between specific metric events. You can use this report to understand the number of click-throughs that generate sales, and the number of units sold. For example, a [!UICONTROL Products Conversion] report shows the percent of Carts events related to Visits events, and then displays totals for Orders, Revenue, and Units based on those events.

<!-- 

c_reports_conversion_funnel.xml

 -->

The following funnel reports are available:

* [!UICONTROL Purchase Conversion Funnel]: Shows Visits (Report-Specific), Carts, Orders, Units, and Revenue.
* [!UICONTROL Cart Conversion Funnel]: Displays Visits (Report-Specific), Carts, Checkouts, Orders, and Revenue.
* [!UICONTROL Custom Event Funnel]: Displays custom events on your site. It shows custom events 1-5 by default.
* [!UICONTROL Campaign Conversion Funnel]: Shows Click-throughs, Checkouts, Orders, and Revenue.

The report table shows statistics for average sales per click-through, and average units sold per click-through. You can add metrics and custom events from other reporting groups to these reports. These funnels have many similarities but are based on different variables and events. You can use these reports to see what percentages and general trends of users fire specific events you specify. You can see where users are not following through to events, which provides insight to that specific point in the conversion process.

## Site Analysis Report {#concept_65694C6BDE424714B7975764F95497A4}

[!UICONTROL Site Analysis] displays how visitors move through specified pages and events. For example, you can see the flow of traffic between pages, the affinity between products and marketing channels, and how campaigns and channels flow to product orders. You can drag pages, dimension items (and lists), and metric events. Each cylinder represents one or more dimension items (pages) or an event. Arrows represent the flow between the cylinder values. Metrics are assigned to cylinder positions (X and Y), cylinder width, cylinder height, and color. The position, size, and color changes depending on the metric values.

<!-- 

c_reports_site_analysis.xml

 -->

Drag items from tool panes to add them to the graph or the dimensions field.

Right click cylinders to edit or remove them.

<!-- Meike, UICONTROL and DNL stripped from tables. Re-add. -->

| Option  | Description  |
|--- |--- |
|Show Site Analysis At (Visit or Visitor)|Lets you switch between  Visit and  Visitor to analyze visitor pathing. These settings help you understand visitor engagement at the visitor level, across visits. Site Analysis, Flow, and Fallout reports are enabled for visitor pathing. Changing this setting reruns the report, constraining the data to the selection.|
|Add Checkpoint|Displays the  Checkpoint Editor, from which you can select dimensions or events to add to the display.|
|Replace Chart|Replaces the  Site Analysis chart with the checkpoints you add to the editor.|
|Fit to Screen|Restores a chart's original view.|
|Aerial View|Provides a topdown view of the chart.|
|Toggle Grid|Toggles the grid on or off.|
|Dimension|The item on which you are reporting. Drag the item from Dimensions.|

| Option  | Description  |
|--- |--- |
|Edit|Lets you add or remove pages to a cylinder.|
|Remove|Lets you remove a cylinder.|
|Reports|Lets you launch another report from the cylinder.|
|Save Chart As|Lets you save the chart as a  .png or  .jpg. If you change the chart controls (graph angle, size) before saving, the changes are preserved in the output.|
|Copy Chart to Clipboard|Copies the chart for pasting into another application. If you change the chart controls (graph angle, size) before saving, the changes are preserved in the output.|
