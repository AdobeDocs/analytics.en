---
title: Conversions reports in Adobe Analytics
description: Learn how to use conversions reports in Adobe Analytics.
feature: Third-party Integration
exl-id: 315b7dc0-1cd9-4beb-8203-88e205375f84
---
# Conversions reports

A 'conversion' is an action that a visitor does on your site that directly translate to your organization's key indicators. Conversions reports show details on how visitors are converting.

This page assumes the user has a basic knowledge of using Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Goals reports

Goals provide Google Analytics users a way to define a website's conversion. They are the default way to create funnels, reverse behavioral flow, multi-channel funnels, and attribution. Goals in Google Analytics are not retroactive, and can only be set up on the admin page. In addition, they are based on only a page, event, time spent, or average number of pages.

In Adobe Analytics, the concept of a goal is not required because metrics can be applied in any context. As long as your implementation accommodates the events you want to track, you can tweak any conversion report and immediately get results for historical data.

### Funnel Visualization

The funnel visualization report helps analysts focus on a particular series of steps required to convert. For example, before making a purchase, a visitor on an ecommerce site would need to access the shopping cart, billing and shipping page, payment page, and order review page.

In Analysis Workspace, this data can be viewed using the Fallout visualization.

1. Click the visualizations icon on the left, and drag a Fallout visualization onto the workspace above the freeform table
2. Click the components icon on the left, then locate the **Pages** dimension.
3. Click the arrow icon next to the Pages dimension to reveal page values. Dimension items are colored yellow.
4. Locate the desired page to act as the first touchpoint, and drag it into the space labeled 'Add Touchpoint' in the visualization.
5. Continue adding desired touchpoints by dragging page values onto the visualization.

The Fallout visualization is not limited to just the Pages dimension. Any dimension, metric, or segment can be used to tailor your fallout report to meet your organization's needs.

![Fallout visualization](/help/technotes/ga-to-aa/assets/fallout.png)

## Ecommerce reports

Ecommerce reports are typically used by sites selling products or services to measure orders and revenue on items purchased. This feature is available in Adobe Analytics, and is known as Products reports.

Both ecommerce reports in Google Analytics and product reports in Adobe Analytics require customized implementation changes to use. See the [Products](/help/components/dimensions/product.md) dimension in the Components user guide for more information.

## Multi-Channel Funnel reports

Multi-channel funnel reports provide additional marketing channel data beyond what acquisition reports provide. These reports focus on how visitors convert, instead of how visitors arrive to your site.

>[!NOTE]
>
> The use of multi-channel reports in Adobe Analytics requires both the setup of Marketing Channels and a custom implementation to accommodate the products variable and purchase event. Adobe recommends working with an implementation consultant if these features are not yet configured for your report suite.

### Multi-Channel - Assisted Conversions

Assisted conversions shows how many times each channel assisted with a conversion. In Analysis Workspace, the **Order Assists** metric can be used.

1. In the Components menu, locate the **Marketing Channel** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the **Order Assists** metric on top of the automatically created **Occurrences** metric header to replace it. Additional metrics can be dragged onto the workspace if wanted.

### Multi-Channel - Top Conversion Paths

The top conversion paths report shows the top channel paths a user takes before converting. Analysis Workspace uses a flow report to visualize top conversion paths.

1. Click the Panels icon on the left, and drag an Attribution panel above the freeform table.
2. Click the Components icon on the left, locate the **Marketing Channel** dimension, and drag it to the box labeled 'Add Dimension'.
3. Locate the desired conversion event under Metrics (e.g. Orders), and drag it to the box labeled 'Add Metric'. Note that calculated metrics are not supported for the Attribution panel.
4. Click Build.
5. In the resulting report, locate the 'Channel Flow' visualization. This flow shows the top paths a visitor touched prior to a purchase.

This flow visualization is interactive. Click each channel to expand the flow in either direction.

![Flow visualization](/help/technotes/ga-to-aa/assets/flow.png)

### Multi-Channel - Time Lag

The time lag report shows the amount of time in days it took for a visitor to convert on your site. In Analysis Workspace, this data is available using the **Days Before First Purchase** dimension. It is only available in context of a correctly implemented purchase event.

1. In the Components menu, locate the **Days Before First Purchase** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Adobe recommends using the **Orders**, **Units**, or **Revenue** metrics with this dimension.

For other types of conversions, including custom events, the **Time Prior to Event** dimension is available. It shows the amount of time, in minutes, it took for a visitor to trigger the event within the visit.

1. In the Components menu, locate the **Time Prior to Event** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Adobe recommends using this dimension alongside custom events or purchase events.

### Multi-Channel - Path Length

The path length report shows the number of channels touched before a conversion event. In Analysis Workspace, the Attribution panel contains this data in one of its visualizations.

1. Click the Panels icon on the left, and drag an Attribution panel above the freeform table
2. Click the Components icon on the left, locate the **Marketing Channel** dimension, and drag it to the box labeled 'Add Dimension'.
3. Locate the desired conversion event under Metrics (e.g. Orders), and drag it to the box labeled 'Add Metric'. Note that calculated metrics are not supported for the Attribution panel.
4. Click Build.
5. In the resulting report, locate the 'Touchpoints per Journey' visualization. This histogram shows the number of channels a visitor touched prior to a purchase.
