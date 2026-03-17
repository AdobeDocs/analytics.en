---
title: Attribution Panel
description: Learn how to use and interpret the attribution panel in Analysis Workspace.
feature: Attribution
role: User, Admin
exl-id: 96ce3cb9-7753-4ec0-b551-e70a1508e3b7
---
# Attribution panel {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_attribution_button"
>title="Attribution"
>abstract="Quickly compare and visualize any number of attribution models using any dimension and conversion metric"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ panel"

>[!CONTEXTUALHELP]
>id="workspace_attribution_panel"
>title="Attribution panel"
>abstract="Quickly compare and visualize any number of attribution models using any dimension and conversion metric.<br/><br/>**Parameters**<br/>**Channel**<br/>The dimension to attribute against. This dimension can be marketing channels, campaigns, or any other dimension.<br/>**Models**<br/>The model determines how credit is assigned to touchpoints.<br/>**Lookback window**<br/>This setting determines the window of data attribution that applies to each conversion."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ panel"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_This article documents the Attribution panel in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_See [Attribution panel](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/attribution) for the_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** version of this article._

>[!ENDSHADEBOX]

The **[!UICONTROL Attribution]** panel is an easy way to build an analysis comparing various attribution models. The panel provides you with a dedicated workspace to use and compare attribution models.

Adobe Analytics enhances attribution by letting you:

* Define attribution beyond paid media: Any dimension, metric, channel or event can be applied to models (for example, internal search), not just marketing campaigns.
* Use unlimited attribution model comparison: dynamically compare as many models as you want.
* Avoid implementation changes: With report-time processing and context-aware sessions, customer journey context can be built in and applied at run time.
* Construct the session that best matches your attribution scenario.
* Break down attribution by segments: Easily compare the performance of your marketing channels across any important segment (for example, New vs. Repeat customers, Product X vs. Product Y, Loyalty level or CLV).
* Inspect channel cross-over and multi-touch analysis: Use Venn Diagrams and Histograms, and trend attribution results.
* Analyze key marketing sequences visually: explore paths that led to conversion visually with multi-node flow and fallout visualizations.
* Build calculated metrics: use any number of attribution allocation methods.

## Use

To use an **[!UICONTROL Attribution]** panel:

1. Create an **[!UICONTROL Attribution]** panel. For information about how to create a panel, see [Create a panel](panels.md#create-a-panel).

1. Specify the [input](#panel-input) for the panel.

1. Observe the [output](#panel-output) for the panel.

### Panel input

You can configure the Attribution panel using these input settings:

1. Add a **[!UICONTROL Success metric]** and a dimension from the **[!UICONTROL Channel]** that you want to attribute against. Examples include Marketing Channels or custom dimensions, such as internal promotions.

   ![The Attribution panel window showing several selected dimensions and metrics.](assets/attribution-panel.png)

1. Select one or more [attribution models](#attribution-models) from **[!UICONTROL Included models]**, the [container](#container) from **[!UICONTROL Container]**, and a [lookback window](#lookback-window) from **[!UICONTROL Lookback window]** that you want to use for comparison.

1. Select **[!UICONTROL Build]** to build the visualizations in the panel.

### Panel output

The **[!UICONTROL Attribution]** panel returns a rich set of data and visualizations that compare attribution for the selected dimension and metric.

   ![The Attribution panel visualizations that compare selected metrics and dimensions.](assets/attr_panel_vizs.png)

### Attribution visualizations

The following visualization are part of the panel ouput.

* **Total metric**: The total number of conversions that occurred over the reporting time window, and are attributed to the dimension you selected.
* **Attribution Comparison Bar**: Visually compares the attributed conversions across each of the dimension items from your selected dimension. Each bar color represents a distinct attribution model.
* **Attribution Comparison Table**: Shows the same data as the bar chart, represented as a table. Selecting different columns or rows in this table filters the bar chart as well as several of the other visualizations in the panel. This table acts similar to any other Freeform table in Workspace - allowing you to add components such as metrics, segments, or breakdowns.
* **Overlap Diagram**: A Venn visualization showing the top three dimension items and how often they participate jointly in a conversion. For example, the size of the bubble overlap indicates how often conversions occurred when a person was exposed to both dimension items. Selecting other rows in the adjacent Freeform table updates the visualization to reflect your selection.
* **Performance Detail**: A scatter visualization to compare up to three attribution models visually.
* **Trended Performance**: Shows the trend of attributed conversions for the top dimension item. Selecting other rows in the adjacent Freeform table updates the visualization to reflect your selection.
* **Flow**: Lets you see which channels are interacted with most commonly, and in what order across a person's journey.

## Attribution model

{{attribution-models-details}}

## Container

{{attribution-container}}

## Lookback window

{{attribution-lookback-window}}

## Example

{{attribution-example}}

>[!MORELIKETHIS]
>
> [Create a panel](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>

<!--
# Attribution panel

The [!UICONTROL Attribution] panel is an easy way to build an analysis comparing various attribution models. It is a feature in [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) that gives you a dedicated workspace to use and compare attribution models.

>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-the-attribution-iq-panel)

## Create an attribution panel

1. Click the panel icon on the left.
1. Drag the [!UICONTROL Attribution] panel into your Analysis Workspace Project.

   ![New attribution panel](assets/Attribution_Panel_1.png)

1. Add a metric that you want to attribute and add any dimension to attribute against. Examples include Marketing Channels or custom dimensions, such as internal promotions.

   ![Select dimension and metric](assets/attribution_panel2.png)

1. Select the [attribution models and lookback window](../attribution/models.md) you want to compare.

1. The Attribution panel returns a rich set of data and visualizations that compare attribution for the selected dimension and metric.

   ![Attribution visualizations](assets/attr_panel_vizs.png)

## Attribution visualizations

* **Total metric**: The total number of conversions that occurred over the reporting time window. These are the conversions that are attributed across the dimension that you selected.
* **Attribution Comparison Bar**: Visually compares the attributed conversions across each of the dimension items from your selected dimension. Each bar color represents a distinct attribution model.
* **Attribution Comparison Table**: Shows the same data as the bar chart, represented as a table. Selecting different columns or rows in this table filters the bar chart as well as several of the other visualizations in the panel. This table acts similar to any other Freeform Table in Workspace - allowing you to add components such as metrics, segments, or breakdowns.
* **Overlap Diagram**: A Venn Diagram showing the top three dimension items and how often they participate jointly in a conversion. For example, the size of the bubble overlap indicates how often conversions occurred when a visitor was exposed to both dimension items. Selecting other rows in the adjacent Freeform table updates the visualization to reflect your selection.
* **Performance Detail**: Lets you to compare up to three attribution models visually using a scatter plot.
* **Trended Performance**: By default, shows the conversion performance trend by attribution model for the first dimension listed in the adjacent Freeform table. You can select different dimension rows in the Freeform table to show the trend for the selected dimensions (such as Total Revenue for each attribution model for Social Campaigns and Paid Search). Alternately, you can select cells in the columns for any metric and attribution type combinations in the Freeform table to see the trended performance by dimension value for the specified attribution models (such as Total Revenue by Marketing Channel using Last Touch and First Touch attribution).
* **Flow**: Lets you see which channels are interacted with most commonly, and in what order across a visitor's journey.

-->