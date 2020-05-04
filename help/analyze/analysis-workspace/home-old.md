---
description: How to get started using Adobe Analytics.
keywords: Analysis Workspace
title: Getting Started guide
---

# Analysis Workspace

Analysis Workspace is one of Adobe's flagship tools to make actionable data-based decisions for your organization. The most common visualization, the freeform table, lets you easily create customized reports using dimensions, metrics, segments, and date ranges.

## Prerequisites

[Send data to Adobe Analytics using Adobe Experience Platform Launch](/help/implement/launch/validate-publish-prod.md): Using Analysis Workspace requires a working implementation. Make sure your organization is sending data to Adobe before using the tool. Other implementations, such as DTM or legacy manual implementations, can work as well.

## Pull a basic ranked report in Workspace

Pull a basic ranked report using Analysis Workspace. A ranked report shows an aggregated total view of each dimension value, showing the largest values first. These types of reports are useful to see what components of your site are most effective, such as which pages get the most traffic or what products sell the most.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. Click the 9-square icon in the upper right, then click the colored Analytics logo.
3. In the top navigation bar, click Workspace.
4. Click the 'Create New Project' button.
5. In the modal popup, make sure 'Blank Project' is selected, then click Create.
6. On the left, you should see a list of dimensions, metrics, segments, and date ranges. Locate the Pages dimension (colored orange), and drag it over to the canvas where it says 'Drop a Dimension Here'.
7. Note that if the report suite has data, a report showing the top pages for this month can be seen. Analysis Workspace automatically populated the report with the [Occurrences](/help/components/c-variables/c-metrics/metrics-occurrences.md) metric.
8. Locate the Visits metric (colored green), and drag it either **over** or **next to** the Occurrences metric header (avoid placing it above the metric). If you drag the Visits metric on top of Occurrences, the metric is replaced in reporting. If you drag the Visits metric next to Occurrences, both metrics are displayed side-by-side.
9. If you'd like to save your project, click *[!UICONTROL Project] > [!UICONTROL Save]* in the upper left menu.

## Pull a basic trended report in Workspace

Pull a basic trended report using Analysis Workspace. A trended report shows an over-time view of metrics using the selected date range. These types of reports are useful for identifying trends over time, and can be used to gauge success or failure of business decisions made. For example, you could look at a page views report trended over time to see if a site redesign helped increase or decrease traffic.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. Click the 9-square icon in the upper right, then click the colored Analytics logo.
3. In the top navigation bar, click Workspace.
4. Click the 'Create New Project' button.
5. In the modal popup, make sure 'Blank Project' is selected, then click Create.
6. On the left, you should see a list of dimensions, metrics, segments, and date ranges. Locate the Page Views dimension, and drag it to the small space on the canvas labeled 'Drop a Metric Here'. Avoid dropping it in the space reserved for dimensions (at least for this exercise).
7. Note that if the report suite has data, you should see a basic page views report trended over the current month. Analysis Workspace automatically brought in the 'Day' date range so you can see the trend of page views for the current month.
8. Locate the Week date range (colored purple) in the list of date range components on the left. Click the date range title to expand and see all date range components, or use the search bar.
9. Drag the Week date range on top of the Day date range header on the canvas to replace it.
10. Note that your trended report is now aggregated by week instead of day.
11. If you'd like to save your project, click *[!UICONTROL Project] > [!UICONTROL Save]* in the upper left menu.

## Experiment with the tool

Since Analysis Workspace is a reporting tool, it has no impact on data collection. There are no repercussions to indiscriminately dragging components into a project to see what works. Drag different combinations of dimensions and metrics into your workspace project to see what is available to you.

If you accidentally drag an invalid component to your workspace project or would like to go back a step, press ctrl+Z (Windows) or cmd+Z (Mac) to undo the last action made. You can also start with a clean slate by clicking *[!UICONTROL Project] > [!UICONTROL New]* in the upper left menu.

## Troubleshooting

**When I drag a metric over, it says 'Invalid data'.**

Invalid data means that Adobe cannot return data using the combination of dimensions and metrics used in the report. For example, two metrics stacked on top of each other cannot be returned as data, as there is no way to display two metrics that way. Instead, place the metrics side-by-side.

**When I drag a metric over, I don't see any actual data - just zeros.**

If you successfully create a workspace report but there's no data, there are a few things you can check:

* Double check the report suite and make sure it's one populated with data.
* If you're using a segment in your report, the segment criteria might not match any data. Try removing the segment or adjusting the segment definition.
* Check the date range in the upper right and make sure it's set to a value that you'd expect.
* Navigate to your website and use the Debugger to validate that data is being collected.

## Additional Resources

* [Analysis Workspace release notes](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md): Read up on the latest features introduced into the tool.
* [Analysis Workspace on YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): Learn how to use most features in Analysis Workspace via this extensive playlist.
* In-product tips: Tips of the day, along with short videos, occasionally appear in the lower right corner of Analysis Workspace. If these tips are dismissed, they can be reached through *[!UICONTROL Help] > [!UICONTROL Tips]* at any time.
* [Analysis Workspace community](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace): Discuss Analysis Workspace with fellow users, and vote on features you'd like to see in the tool.
* Blog posts:
  * [Empowering Organizations with Smarter Analysis](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
  * [New Adobe Analytics Capabilities Make Powerful Insights More Accessible](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
  * [5 Tips to Maximize Your Productivity with Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
  * [Faster Insights with Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
  * [Why You Should Be Using Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## Next steps

There are a lot of directions to go to deepen your understanding of Analysis Workspace. Here are some basics that Adobe recommends:

### For end users looking to expand knowledge on how to use Analysis Workspace

* [Details on the Workspace UI](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md): Now that you've created a basic report, become more familiar with the rest of the interface.
* [Visualizations in Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md): Freeform tables are merely one type of visualization in Analysis Workspace. Learn how to use other visualizations, such as line charts, bar graphs, and geo maps.
* [Dimensions in Workspace](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): Learn more about what dimensions are and how to use them in more than just ranked reports.
* [Metrics in Workspace](/help/analyze/analysis-workspace/components/apply-create-metrics.md): Learn more about what metrics are and how to use them in other parts of freeform tables.
* [Introduction to segmentation](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md): Learn about what segments are and pull a basic report using a segment.
* [Date ranges in Workspace](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): Learn about relative and rolling dates, and use them in workspace projects.
* Sharing projects in Workspace: Show your colleague the awesome Workspace project you created.
* [(Advanced) Panels in Workspace](/help/analyze/analysis-workspace/c-panels/panels.md): Use advanced features in Workspace, such as Attribution and Segment Comparison.

### For analysts and admins looking to improve the quality of Workspace in their organization

* [Analysis Workspace permissions](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html): Assign users permissions to Workspace via the Adobe Admin Console.
* [Templates in Workspace](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md): Create templates so your colleagues can start with a project space tailored to their needs.
* [Workspace curation](/help/analyze/analysis-workspace/curate-share/curate.md): Create a project that limits available components, making workspace more accessible to those less familiar with the tool
