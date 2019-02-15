---
description: Displays information about the order in which pages of your website are accessed. You can gather information about where a visitor goes before and after any page visited on your site.
seo-description: Displays information about the order in which pages of your website are accessed. You can gather information about where a visitor goes before and after any page visited on your site.
seo-title: Paths reports
solution: Analytics
title: Paths reports
topic: Ad hoc analysis
uuid: 5881cb1c-6d66-49fe-ac84-70b82662acd2
---

# Paths reports

Displays information about the order in which pages of your website are accessed. You can gather information about where a visitor goes before and after any page visited on your site.

## Paths reports {#concept_CB32E270FB9E4D929C91FDFE428CB224}

Displays information about the order in which pages of your website are accessed. You can gather information about where a visitor goes before and after any page visited on your site. 

Paths reports include standard in-depth and optional advanced analysis reports that reveal the click-stream of pages viewed. You can uncover full paths, longest paths, and most popular paths; explain page flow, fallout, and dropout graphically; show new and changing patterns over time; and analyze entry and exit paths.

** [!UICONTROL Next Page Flow] ** or ** [!UICONTROL Next Site Flow]**: Displays a two-level-deep branching graphic of a selected page (or section, department, and so on), that your visitors view after moving away from the selected page. Use this report to analyze and identify the steps your visitors take most often after viewing a selected page. You can:

* Understand what steps are taken most frequently after viewing a selected page. 
* Optimize your site path design to funnel your traffic to a desired goal page. 
* Identify where visitors are going instead of your desired goal pages.

** [!UICONTROL Next Page] ** (or next categories): Provides detailed site path analysis by showing you the pages on your site that visitors viewed after seeing a selected page. For example, when selecting and reporting on your entire site, the report shows you the top ten landing pages, with the five most popular next pages listed below each landing page. This data can help you understand which content, features, and other data, most often compel your visitors to move through your site.

** [!UICONTROL Previous Page Flow] ** (or other previous categories flow): Displays two levels of the most popular pages that your visitors view before the selected page. The report also highlights when visitors enter your site.

** [!UICONTROL Previous Page] ** (or other previous categories): Provides detailed site path analysis by showing you the pages on your site that visitors viewed before seeing a selected page on your site.

** [!UICONTROL Fallout] **: Displays the visit attrition and conversion rates between each checkpoint you define. Steps are arranged top-to-bottom, with raw numbers and percentages shown on the left, and conversion and fall-out percentages on the right.

See [Fallout Report](../../analyze/ad-hoc-analysis/c-reports-paths.md#concept_0ED452F3B1D04A19A59DD04D76D20347) for more information.

** [!UICONTROL Path Length] **: Shows how deep visitors browse into your site (both by percentage and by total count). In other words, the report indicates how many pages the average visitor to your site views before leaving.

** [!UICONTROL Page Analysis] **: Contains a subset of reports that let you analyze the following:

* ** [!UICONTROL Page Summary / Site Category Summary] **: Tells you everything you need to know about the page report. It collects and organizes page-specific information about a single page and presents it in a single report. 
* ** [!UICONTROL Reloads] **: Shows the number of times individual pages were reloaded by visitors. 
* ** [!UICONTROL Time Spent on Page / Site Category] **: Displays the length of time that visitors browse individual pages in your site. The time spent is divided into ten categories: less than 15 seconds, 15-30 seconds, 30-60 seconds, 1-3 minutes, 3-5 minutes, 5-10 minutes, 10-15 minutes, 15-20 minutes, 20-30 minutes and greater than 30 minutes. 
* ** [!UICONTROL Clicks to Page] **: Identifies the number of clicks visitors used to access each page in your site. Depth for a page is measured by counting the number of pages viewed before it.

** [!UICONTROL Entries & Exits] **: The [!UICONTROL Entry Page] report shows you, by percentage and by total visits, which pages on your site are the first ones seen by new visitors. You can view:

* ** [!UICONTROL Entry Pages] ** (or sections): Displays, by percentage and by total visits, which pages on your site are the first pages seen by a new visitor. You can use this report to identify which of your web pages are the most frequent points of entry, optimize the primary entry points on your site, and drive entry traffic to your key messages. 
* ** [!UICONTROL Original Entry Pages] **: Shows the first page viewed for first-time visitors to your site. Each user is counted only once unless they delete their cookies or are not being tracked with cookies. 
* ** [!UICONTROL Single Page Visits] **: Shows pages that are most often both the entry and exit pages for visitor browsing sessions. 
* ** [!UICONTROL Exit Pages] **: Displays, by percentage and by total visits, the pages on your site that were the last pages visitors viewed before leaving your site.

## Fallout Report {#concept_0ED452F3B1D04A19A59DD04D76D20347}

The [!UICONTROL Fallout Report] shows where visitors leave (fallout) and continue through (fallthrough) a pre-specified sequence of pages. It displays conversion and fallout rates between each step. For example, you can track a visitor's fallout points during a buying process. You select a beginning point and a conclusion point, and add intermediate points to create a website navigation path.

<!-- 

c_reports_fallout.xml

 -->

You can analyze fallout data at the Visit or Visitor level. You can also see a trended path that shows you a graph of your fallout over a specific period. You can set single or groups of pages as the report checkpoints, or add any dimension or metric in any combination or sequence. You can also use categories that you configure in marketing reports and analytics as checkpoints in this report.

This report is useful to analyze:

* Conversion rates through specific processes on your site (such as a purchase or registration process). 
* General, wider-scope traffic flows: Of the people who saw the home page, this flow shows how many went on to perform a search, and then how many of them eventually went on to look at a specific item. 
* Correlations between events on your site. Correlations show what percentage of people who looked at your privacy policy went on to purchase a product.

## Run a Fallout Report {#task_3594E8BE55964C1C8B0BEC8DEABF82D3}

Steps to run a [!UICONTROL Fallout Report].

<!-- 

t_fallout.xml

 -->

1. Click **[!UICONTROL Reports]** > **[!UICONTROL New Report]** > **[!UICONTROL Fallout.]**

   Other Fallout reports are found in **[!UICONTROL Reports]** > **[!UICONTROL Paths]**. 

1. (Optional) Drag a segment to the [!UICONTROL Drop Segment Here] field, if you want to filter the data by a specific segment.
1. Drag any dimension item to the [!UICONTROL Drop Event or Dimension Items Here] field.
1. Click **[!UICONTROL Show Fallout At]**Visit or Visitor level, depending on whether you want to view fallout at the visit level, or across visitor sessions.
1. Add dimension items, such as pages, to the report.

## Assign Pages to a Fallout Report {#task_B386289703494FA7B5A40FF9F97CB537}

Steps to assign pages to a fallout report.

<!-- 

t_fallout_assign_pages.xml

 -->

1. Click **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Pages Fallout]**.
1. From the [!UICONTROL Dimensions] pane, locate the pages to add, then drag them to the [!UICONTROL Drop Event or Dimension Here] field.

## Fallout Report - Field Descriptions {#reference_74255CC8D6134F349FEBFEC72934C866}

Field descriptions for the [!UICONTROL Fallout] report.

<!-- 

r_dsc_fallout.xml

 -->

| Field | Description |
|--- |--- |
|Show Fallout At Visit or Visitor Level|Lets you switch between Visit and Visitor to analyze visitor pathing. These settings help you understand visitor engagement at the visitor level, across visits. Site Analysis, Flow, and Fallout reports are enabled for visitor pathing. Changing this setting reruns the report, constraining the data to the selection.|
|Total Success|A total indicator of success. This value reflects the value in the last checkpoint of the path.|
|Total Success %|A cumulative total of the percentage of visitors arriving at each checkpoint.|
|Checkpoint %|The percentage of success between checkpoints. (Not cumulative.)|
|Include All Visits|Adds all visits as the initial checkpoint.|
|Fallout|Lets you see the pages viewed after the visitor fell out of the specified checkpoint path.|
|Fallthrough|Lets you see the pages viewed in the next step of the specified checkpoint path.|
