---
description: null
title: Optimize Analysis Workspace performance
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
---

# Optimize Analysis Workspace performance

Certain factors can influence the performance of a project within Analysis Workspace. It's important to know what those contributors are before you start building a project so that you can plan & build the project in the most optimal way. Below is a list of factors that will impact performance & best practices for optimizing your projects. Analysis Workspace performance is one of Adobe's top priorities and something we are continuing to improve each day.

## Complexity of segment logic

Intricate segments can have a significant impact on project performance. Factors that add complexity to a segment (in descending order of impact) include:

* Operators of "contains,", "contains any of", "matches," "starts with," or "ends with"
* Sequential segmentation, especially when dimension restrictions (Within/After) are used
* Number of unique dimension items within dimensions used in the segment (e.g., Page = 'A' when Page has 10 unique items will be faster than Page = 'A' when Page has 100000 unique items)
* Number of different dimensions used (e.g., Page = 'Home' and Page = 'Search results' will be faster than eVar 1 = 'red' and eVar 2 = 'blue')
* Many OR operators (instead of AND)
* Nested containers that vary in scope (e.g., "Hit" inside of "Visit" inside of "Visitor")

**Best practices for logic complexity**

While some of the complexity factors cannot be prevented, think about opportunities to reduce the complexity of your segments. In general, the more specific you can be with your segment criteria, the better. For example:

* With containers, using a single container at the top of the segment will be faster than a series of nested containers.
* With operators, "equals" will be faster than "contains", and "equals any of" will be faster than "contains any of".
* With many criteria, AND operators will be faster than a series of OR operators. Also, look for opportunities to reduce many OR statements into a single "equals any of" statement.

In addition, [classifications](/help/components/classifications/c-classifications.md) can help consolidate many values into concise groups from which you can then create segments. Segmentation on classification groups provides performance benefits over segments that contain many OR statements or "contains" criteria.

## Range of data requested

The range of data requested throughout a project will influence Analysis Workspace performance. 

**Best practices for date ranges**

Where possible, don't pull in more data than you need. Narrow the panel calendar to the relevant dates for your analysis, or use date range components (purple components) in your freeform tables. Date ranges used in a table override the panel date range. For example, you can add last month, last week and yesterday to the table columns to request those specific ranges of data. For more information on working with date ranges in Analysis Workspace, watch [this video](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html).

Minimize the number of year-over-year comparisons used in the project. When a year-over-year comparison is calculated, it looks across the full 13 months of data between the months of interest. This has the same impact as changing the panel date range to last 13 months.

## Number of visualizations

The number of  visualizations contained in one project will affect overall responsiveness of Analysis Workspace. This is because each visualization, whether it be a table or graph, has a data source that needs to be requested.

**Best practice for number of visualizations**

Decrease the number of visualizations in your project. Analysis Workspace is doing a lot of processing behind the scenes for each visual that you add, so prioritize the visuals that are most important to the consumer of the report and break out supporting visuals into a separate, more detailed project if needed.

## Complexity of visualizations (segments, metrics, filters)

The type of visualization (e.g. fallout vs a freeform table) added to a project by itself doesn't influence project performance very much. It is the complexity of the visualization that will add to processing time. Factors that add complexity to a visualization include:

* Range of data requested, as mentioned above
* Number of segments applied; for instance, segments used as rows of a freeform table
* Use of intricate segments
* [Static item](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) rows or columns in freeform tables
* Filters applied to rows in freeform tables
* Number of metrics included, especially calculated metrics that use segments

**Best practice for visualization complexity**

If you notice that your projects aren't loading as quickly as you'd like, try replacing some segments with eVars and filters, where possible.

If you find yourself constantly using segments and calculated metrics for data points that are important to your business, consider improving your implementation to capture these data points more directly. The use of a tag manager like Adobe Experience Platform Launch and Adobe's processing rules can make implementation changes quick & easy to implement. To better understand how to simplify intricate segments, see 'Complexity of Segment Logic' above.

## Number of panels

One panel can contain many visualizations, and as a result, the number of panels can also influence the overall responsiveness of Analysis Workspace.

**Best practice for number of panels**

Don't try to add everything into one project, but rather create distinct projects that serve a specific purpose or group of stakeholders. Use tags to organize projects into key themes and share related projects with groups of stakeholders.

If more organization of projects is desired, remember that [direct linking](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/curate-and-share-projects/direct-link-to-a-project.html) to your project is an option. Create an internal index of projects so that stakeholders can more easily find what they need.

If many panels are needed in one project, collapse panels before saving and sharing. When a project is loaded, Analysis Workspace will only load content for the expanded panels. Collapsed panels will not be loaded until the user expands them. This approach helps in two ways:

* Collapsed panels save on overall load time of a project
* Collapsed panels are a great way to organize your projects in a logical way for the consumer of the report

## Report suite size

The size of the report suite may seem like a driving factor, but in reality it only plays a small role in project performance due to how Adobe handles data processing. There can be exceptions to this rule; consult with your implementation team or an Adobe expert to determine if there are implementation improvements that can be made to improve overall experience in Adobe Analytics.

## Number of users concurrently accessing Analysis Workspace

The number of users accessing Analysis Workspace or specific projects at the same time does not have a substantial effect on Analysis Workspace performance, if users are accessing different report suites. If concurrent users are accessing the same report suite, performance will be impacted.

## Common error messages in Analysis Workspace

You may encounter errors when interacting with Analysis Workspace. Errors can occur for several reasons and listed below are the most common ones.

| Error message | Why does this occur? |
| --- | --- |
| *[!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.]* | Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, scheduled reports, scheduled alerts, and concurrent users making reporting requests. We recommend that your requests and schedules for the report suite be spread more evenly throughout the day. |
| *[!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.]* | Adobe is experiencing an issue that needs to be resolved. We recommend that you submit the error code through a Customer Care request. |
| *[!UICONTROL The request is too complex.]* | Your reporting request is too large and cannot be executed. Contributors to this error are timeouts due to the request's size, too many matched items in a segment or search filter, too many metrics included, incompatible dimension and metric combinations, etc. We recommended that you simplify your request. |
| *[!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.]* | We recommend narrowing your search text criteria and trying the request again. |
| *[!UICONTROL This dimension does not currently support non-default attribution models.]* | We recommend replacing the dimension in your table with one that is compatible with [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md). |
| *[!UICONTROL Your request failed as a result of too many columns or pre-configured rows.]* | We recommend removing some of the columns or rows, or consider splitting them into separate visualizations. |
