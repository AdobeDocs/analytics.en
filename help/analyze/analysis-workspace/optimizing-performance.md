---
description: null
seo-description: null
seo-title: Optimize Workspace performance
title: Optimize Workspace performance
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
---

# Optimize Workspace performance

Certain factors can influence the performance of a project within Analysis Workspace. It’s important to know what those contributors are before you start building a project so that you can plan & build the project in the most optimal way. Below is a list of factors that will impact performance & best practices for optimizing your projects. Analysis Workspace performance is one of Adobe’s top priorities and something we are continuing to improve each day. 

## Complexity of Segment Logic

Intricate segments can have a significant impact on project performance. Factors that add complexity to a segment (in approximate order of impact) include:

* Operators of “contains,”, "contains any of", “matches,” “starts with,” or “ends with"
* Sequential segmentation, especially when dimension restrictions (Within/After) are used
* Number of unique dimension items within dimensions used in the segment (e.g., Page = 'A' when Page has 10 unique items will be faster than Page = 'A' when Page has 100000 unique items)
* Number of different dimensions used (e.g., Page = 'Home' and Page = 'Search results' will be faster than eVar 1 = 'red' and eVar 2 = 'blue')
* Many OR operators (instead of AND)
* Nested containers that vary in scope (e.g., Hit inside of Visit inside of Visitor)

### Best Practice

While some of the complexity factors cannot be prevented, think about opportunities to reduce the complexity of your segments. In general, the more specific you can be with your segment criteria, the better. For example:

* With containers, using a single container at the top of the segment will be faster than a series of nested containers.
* With operators, "equals" will be faster than “contains”.
* With many criteria, AND operators will be faster than a series of OR operators.

In addition, [classifications](/help/components/c-classifications2/c-classifications.md) can help consolidate many values into concise groups from which you can then create segments. Segmentation on classification groups provides performance benefits over segments that contain many OR statements or “contains” criteria. 

## Range of data requested

The range of data requested throughout a project will influence Analysis Workspace performance.

### Best Practice

Where possible, don’t pull in more data than you need.

Remember that date ranges (purple components) override the panel date range. As a result, if you are using different date ranges as columns (e.g. last month, last week and yesterday columns), the panel date range does not have to span all of the column date ranges. It can simply be set to yesterday, because the data ranges used in the freeform table will override the panel. For more information on working with date ranges in Analysis Workspace, watch [this video](https://www.youtube.com/watch?v=ybmv6EBmhn0) .

Use [date comparison options](../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764) to pull in the specific time periods of data you want to compare. For example, if you need to show last month's data compared to same month last year, rather than setting the panel to the last 13 months of data, simply use the compare time periods option to show year-over-year performance.

## Number of visualizations

The number of graph visualizations contained in one project will affect overall responsiveness of Analysis Workspace. 

### Best Practice

Decrease the number of visualizations in your project. Analysis Workspace is doing a lot of processing behind the scenes for each visual that you add, so prioritize the visuals that are most important to the consumer of the report and break out supporting visuals into a separate, more detailed project if needed.

## Complexity of visualizations (segments, metrics, filters)

The type of visualization (e.g. fallout vs a freeform table) added to a project by itself doesn’t influence project performance very much. It is the complexity of the visualization that will add to processing time. Factors that add complexity to a visualization include:

* Range of data requested, as mentioned above
* Number of segments applied; for instance, segments used as rows of a freeform table
* Use of intricate segments
* Static item rows or columns in freeform tables
* Filters applied to rows in freeform tables
* Number of metrics included, especially calculated metrics that use segments

### Best Practice

If you notice that your projects aren't loading as quickly as you'd like, try replacing some segments with eVars and filters, where possible.

If you find yourself constantly using segments and calculated metrics for data points that are important to your business, consider improving your implementation to capture these data points more directly. The use of a tag manager like Adobe Launch and Adobe’s processing rules can make implementation changes quick & easy to implement. To better understand how to simplify intricate segments, see 'Complexity of Segment Logic' above. 

## Number of panels

One panel can contain many visualizations, and as a result, the number of panels can also influence the overall responsiveness of Analysis Workspace.

### Best Practice

Don’t try to add everything into one project, but rather create distinct projects that serve a specific purpose or group of stakeholders. Use tags to organize projects into key themes and share related projects with groups of stakeholders.

If more organization of projects is desired, remember that [direct linking](https://www.youtube.com/watch?v=6IOEewflG2U) to your project is an option. Create an internal index of projects so that stakeholders can more easily find what they need. Additionally, Adobe is actively looking into bringing more organization options to Analysis Workspace.

If many panels are needed in one Workspace, collapse panels before saving and sharing. When a project is loaded, Analysis Workspace will only load content for the expanded panels. Collapsed panels will not be loaded until the user expands them. This approach helps in two ways:

* Collapsed panels save on overall load time of a project
* Collapsed panels are a great way to organize your projects in a logical way for the consumer of the report

## Report suite size

The size of the report suite may seem like a driving factor, but in reality it only plays a small role in project performance due to how Adobe handles data processing

## Number of people concurrently accessing Analysis Workspace

The number of people accessing Analysis Workspace or specific projects at the same time does not have a substantial effect on Analysis Workspace performance.