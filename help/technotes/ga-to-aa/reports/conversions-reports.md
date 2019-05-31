---
title: Conversions reports in Adobe Analytics
description: Learn how to use conversions reports in Adobe Analytics.
---

# Conversions reports

A 'conversion' is an action that a visitor does on your site that directly translate to your organization's key indicators. Conversions reports show details on how visitors are converting.

This page assumes the user has a basic knowledge of using Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Goals reports

Goals provide a Google Analytics users with a way to define a website's conversion. Goals are the default way to create Funnels, reverse Behavioral Flow, Multi-Channel Funnels, and Attribution are created in Google Analytics. However, Goals are difficult to work with because they are not retroactive, are based on only a page, event, time spent, or average number of pages, and can only be set up in the admin page. 

In Adobe Analytics, the concept of a Goal is not required since metrics (standard or calculated) can be applied in Funnels (Fallout in Adobe), reverse Behavioral Flow (Flow in Adobe), Multi-Channel Funnels (Marketing Channels in Adobe), and Attribution (Attribution IQ). Calculated metrics in Adobe Analytics are retroactive too, making them even more useful to you.

### Funnel Visualization

The Funnel Visualization report in Google Analytics is built to help analysts prescriptively analyze data - focusing on a particular series of steps required to convert. For example, before making a purchase, a visitor on an ecommerce site would need to access the shopping cart, billing and shipping page, payment page, and order review page. In Google Analytics, these steps are defined in the Goal setup in the administration console and are not retroactive - meaning data will only populate in the Funnel Visualization report starting on the day you define the Funnel steps in the administration console.

In Analysis Workspace, the Fallout visualization will be your preferred method for accomplishing this analysis. Most importantly, the Fallout visualization does not need to be set up in the admin console like in Google Analytics. Instead, they are defined on the fly, using a potential mixture of metrics, dimensions, and segments. Since they are built in real time, the data is completely retroactive, meaning you always have the flexibility to change the components of the Fallout.


### Goal Flow and Reverse Goal Path

The Goal Flow report in Google Analytics is built to help you answer questions about the flow towards a conversion. It helps answer questions like:
- Are there a lot of unexpected exits frmo a step in the middle of the funnel?
- Is there one segment of traffic that acts differently than other segments?
These questions and more are asked by analysts every day. 

The Reverse Goal Path report is used to show the 3 previous pages to a Goal's completion.

These two reports are perhaps the only reports in Google Analytics that allow analysts to start their analysis with a conversion and work backwards. However, in the Goal Flow report, that analysis is limited to just the Goal's funnel plus 1 dimension in the admin console. In the Reverse Goal Path report, the analysis is limited to just the 3 previous pages to the Goal's completion and no other dimensions can be used.

In Analysis Workspace, the Fallout visualization can be used to to answer similar questions and more. Most importantly, the Fallout visualization does not need to be set up in the admin console like in Google Analytics. Instead, they are defined on the fly, using a potential mixture of metrics, dimensions, and segments. Since they are built in real time, the data is completely retroactive, meaning you always have the flexibility to change the components of the Fallout.

## Ecommerce reports

Ecommerce reports are typically used by sites selling products or services to measure orders and revenue on items purchased. This feature is available in Adobe Analytics, and is known is Products reports.

Both Ecommerce reports in Google Analytics and Product reports in Adobe Analytics require customized implementation changes to use. See the [Products](../../../components/c-variables/dimensionslist/reports-products.md) dimension in the Components user guide for more information.

## Multi-Channel Funnel reports

Multi-channel funnel reports provide additional marketing channel data beyond what acquisition reports provide. These reports focus on how visitors convert, instead of how visitors arrive to your site.

> [!NOTE]
>
> The use of multi-channel reports in Adobe Analytics requires both the setup of Marketing Channels and a custom implementation to accommodate the products variable and purchase event. Adobe recommends working with an implementation consultant if these features are not yet configured for your report suite.

### Multi-Channel - Assisted Conversions

Assisted conversions shows how many times each channel assisted with a conversion. In Analysis Workspace, the `Order Assists` metric can be used.

1. In the Components menu, locate the `Marketing Channel` dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the `Order Assists` metric on top of the automatically created `Occurrences` metric header to replace it. Additional metrics can be dragged onto the workspace if wanted.

### Multi-Channel - Top Conversion Paths

The top conversion paths report shows the top channel paths a user takes before converting. Analysis Workspace uses a flow report to visualize top conversion paths.

1. Click the Panels icon on the left, and drag an Attribution panel above the freeform table.
2. Click the Components icon on the left, locate the `Marketing Channel` dimension, and drag it to the box labeled 'Add Dimension'.
3. Locate the desired conversion event under Metrics (e.g. Orders), and drag it to the box labeled 'Add Metric'. Note that calculated metrics are not supported for the Attribution panel.
4. Click Build.
5. In the resulting report, locate the 'Channel Flow' visualization. This flow shows the top paths a visitor touched prior to a purchase.

This flow visualization is interactive. Click each channel to expand the flow in either direction.

### Multi-Channel - Time Lag

The time lag report shows the amount of time in days it took for a visitor to convert on your site. In Analysis Workspace, this data is available using the `Days Before First Purchase` dimension. It is only available in context of a correctly implemented purchase event.

1. In the Components menu, locate the `Days Before First Purchase` dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created `Occurrences` metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Adobe recommends using the `Orders`, `Units`, or `Revenue` metrics with this dimension.

For other types of conversions, including custom events, the `Time Prior to Event` dimension is available. It shows the amount of time, in minutes, it took for a visitor to trigger the event within the visit.

1. In the Components menu, locate the `Time Prior to Event` dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created `Occurrences` metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Adobe recommends using this dimension alongside custom events or purchase events.

### Multi-Channel - Path Length

The path length report shows the number of channels touched before a conversion event. In Analysis Workspace, the Attribution panel contains this data in one of its visualizations.

1. Click the Panels icon on the left, and drag an Attribution panel above the freeform table
2. Click the Components icon on the left, locate the `Marketing Channel` dimension, and drag it to the box labeled 'Add Dimension'.
3. Locate the desired conversion event under Metrics (e.g. Orders), and drag it to the box labeled 'Add Metric'. Note that calculated metrics are not supported for the Attribution panel.
4. Click Build.
5. In the resulting report, locate the 'Touchpoints per Journey' visualization. This histogram shows the number of channels a visitor touched prior to a purchase.
