---
title: Concurrent Viewers panel
description: How to use and interpret the Concurrent Viewers panel in Analysis Workspace.
---

# Concurrent Viewers panel


** REVISE CONTENT FOR NEW Concurrent Viewers FEATURE - this sample content is copied from the attribution panel **


THIS IS A PLACEHOLDER PAGE

The attribution panel is an easy way to build an analysis comparing various attribution models. It is a feature in [Attribution IQ](../attribution/overview.md) that gives you a dedicated workspace to use and compare attribution models.

## Create an attribution panel

1. Click the panel icon on the left.
1. Drag the Attribution Panel into your Analysis Workspace Project.

   ![New attribution panel](assets/Attribution_Panel_1.png)

1. Add a metric that you want to attribute and add any dimension to attribute against. Examples include Marketing Channels or custom dimensions, such as internal promotions.

   ![Select dimension and metric](assets/attribution_panel2.png)

1. Select the [attribution models and lookback window](../attribution/models.md) you want to compare.

1. The Attribution panel returns a rich set of data and visualizations that compare attribution for the selected dimension and metric.

   ![Attribution visualizations](assets/attr_panel_vizs.png)

## Attribution visualizations

* **Total metric**: The total number of conversions that occurred over the reporting time window. These are the conversions that are attributed across the dimension you selected.
* **Metric Attribution Comparison Bar Chart**: Visually compares the attributed conversions across each of the dimension items from your selected dimension. Each bar color represents a distinct attribution model.
* **Metric Attribution Freeform Table**: Shows the same data as the bar chart, represented as a table. Selecting different columns or rows in this table filters the bar chart as well as several of the other visualizations in the panel. This table acts similar to any other Freeform Table in Workspace - allowing you to add compoents such as metrics, segments, or breakdowns.
* **Dimension Overlap Chart**: A Venn Diagram showing the top three dimension items and how often they participate jointly in a conversion. For example, the size of the bubble overlap indicates how often conversions occurred when a visitor was exposed to both dimension items. Selecting other rows in the adjacent Freeform table updates the visualization to reflect your selection.
* **Marketing Touchpoints Per Journey**: A histogram indicating the number of touchpoints a visitor had in the lookback window. This is useful to see how impactful multi-touch attribution is for your dataset. If nearly all visitors have only a single touchpoint, different attribution models likely show similar data.
* **Marketing Channel Performance Detail**: Lets you to compare up to three attribution models visually using a scatter plot.
* **Marketing Channel Flow**: Lets you see which channels are interacted with most commonly, and in what order across a visitor's journey.
