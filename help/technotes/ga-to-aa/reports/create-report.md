---
title: Create a basic report in Analysis Workspace
description: Learn how to create a basic report in Analysis Workspace in a format geared towards users familiar with third-party tools such as Google Analytics.
feature: Third-party Integration
exl-id: 513da3f1-ad24-4d5b-bc35-dbcd3694cbdf
TQID: https://experienceleague.adobe.com/huQkwfObQW132aNeBiEMuPPeJ5H-6UaaVdJX77dHHUY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
    internal-label: Panels
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Create a basic report in Analysis Workspace for Google Analytics users

Analysis Workspace (one of the main features within Adobe Analytics) provides a robust area for a user to gain any insight on collected data. Reporting is very different between Google Analytics and Adobe Analytics:

* The reporting structure in Google Analytics allows you to select a particular type of data, such as geo location or referral traffic. The platform uses a prefabricated reporting view based on the anticipated best way to view that data.
* The reporting structure in Analysis Workspace provides a blank canvas, providing more flexibility in meeting exact reporting needs.

Because Analysis Workspace works more like a canvas than prefabricated reports, recreating reports from Google Analytics is simply a matter of using the right visualizations and components.

## Key terms used in Workspace

* **Panels** are the overarching building blocks of workspace. In almost all scenarios, a Freeform panel is used.
* **Visualizations** make up all freeform panels. Their purpose is to represent data in different formats. Most of the time that format is a table, but other times it can be things like a donut or line chart. Many reports in Google Analytics are made of the equivalent of two visualizations: a line chart and freeform table.
* **Components** are placed in a visualization to return data. Components can be mixed in many different ways to meet reporting needs.
  * **Dimensions** are variable values, and typically contain text. Examples include page name, referrer, or geo country. They are most commonly listed as rows in a table.
  * **Metrics** typically signify an event or conversion of some sort. Examples include common events such as a page view, or something more significant like a purchase or registration. They are most commonly seen as columns in tables to show the number of times that event occurred per dimension.
  * **Segments** are a subset of your data, and behave similarly to segments in Google Analytics. They allow you to make customized filters, allowing you to focus on a specific part of your data.
  * **Date ranges** let you organize data by when an event occurred. They are the backbone of viewing trends over time, and are typically paired with a metric.

## Create a basic report in Workspace

Create an All Pages report (similar to the one in Google Analytics) by dragging the right components onto a workspace canvas.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. Click the 9-square icon in the upper right, then click the colored Analytics logo.
1. In the top navigation bar, click Workspace.
1. Click the 'Create New Project' button.
1. In the modal popup, make sure 'Blank Project' is selected, then click Create.
1. On the left, a list of dimensions, metrics, segments, and date ranges is shown. Locate the Pages dimension (colored orange), and drag it onto the canvas labeled 'Drop a Dimension Here'.
1. A report showing the top pages for this month can be seen. Analysis Workspace automatically populates the report with the [Occurrences](/help/components/metrics/occurrences.md) metric.
1. A table in Google Analytics typically contains 7-8 metrics. Locate the Bounce Rate metric (colored green), and drag it next to the Occurrences metric header. If you drag the Bounce Rate metric next to Occurrences, both metrics are displayed side-by-side.
1. Many metrics can be placed side-by-side by dragging metrics next to existing metric headers. See [commonly used metrics](common-metrics.md) for information on how to obtain metrics typically used in Google Analytics.

   ![New metric](/help/technotes/ga-to-aa/assets/new_metric.png)

## Start with a pre-built report template in Workspace

Create the Content Consumption template (similar to the All Pages report in Google Analytics) by accessing a project template.

1. Click the 'Create New Project' button.
1. Locate and double-click the 'Content Consumption (Web)' icon listed under All Templates.
1. Browse each of the visualizations that have been pre-built: Entry Page Flow, Top Pages Table, Exit Page Flow, Entry Site Section Flow, and Top Site Sections Table.

   ![Template selection](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Experiment with the tool

Since Analysis Workspace is a reporting tool, it has no impact on data collection. There are no repercussions to indiscriminately dragging components into a project to see what works. Drag different combinations of dimensions and metrics into your workspace project to see what is available to you.

If you accidentally drag an invalid component to your workspace project or would like to go back a step, press ctrl+Z (Windows) or cmd+Z (Mac) to undo the last action made. You can also start with a clean slate by clicking *[!UICONTROL Project] > [!UICONTROL New]* in the upper left menu.

Adobe has placed a lot of functionality in Analysis Workspace in the right-click context menu. Most visualizations and components can be right-clicked for more detailed analysis and interaction. Consider right-clicking components in your workspace to see what options are available.

## Understand what dimensions and metrics to use

If you are comfortable with Analysis Workspace and would like to recreate a specific report typically viewed in Google Analytics, locate the report on its respective page:

* [Real-Time reports](realtime-reports.md)
* [Audience reports](audience-reports.md)
* [Acquisition reports](acquisition-reports.md)
* [Behavior reports](behavior-reports.md)
* [Conversions reports](conversions-reports.md)
