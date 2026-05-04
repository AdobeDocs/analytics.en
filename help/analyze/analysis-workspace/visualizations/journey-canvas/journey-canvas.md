---
description: Learn ho to use the journey canvas in Analysis Workspace.
title: Journey Canvas Overview
feature: Visualizations
role: User, Admin
---
# Journey canvas overview {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="Journey canvas"
>abstract="Shows how people proceed through or fall out of a series of touchpoints. Use for journeys with multiple entry points and paths."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="Journey canvas"
>abstract="Analyze how people proceed through or fall out of a defined journey. Build analyses of user journeys by creating a flexible graph of nodes and arrows representing any combination of events, dimension items, and segments. Drag nodes on the canvas to rearrange the events and conditions of the journey. As you do, data updates accordingly."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_button2"
>title="Journey canvas"
>abstract="Shows how people proceed through or fall out of a series of touchpoints. Use for journeys with multiple entry points and paths."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_panel2"
>title="Journey canvas"
>abstract="Analyze how people proceed through or fall out of a defined journey. Build analyses of user journeys by creating a flexible graph of nodes and arrows representing any combination of events, dimension items, and segments. Drag nodes on the canvas to rearrange the events and conditions of the journey. As you do, data updates accordingly."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_This article documents the Journey canvas visualization in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**.<br/><br/>_See [Journey canvas overview](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas) for the_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** version of this article._

>[!ENDSHADEBOX]

The Journey canvas visualization allows you to analyze and gain deep insights on the journeys that you provide to your users and customers. It allows you to define a journey, then see how people left (fell out) or continued through (fell through) the journey. 

You can [build analyses of user journeys](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) by using any combination of events, dimension items, segments, and date ranges to create journey nodes. Connect the nodes to create the journey's flow, and include multiple paths and decision points. Drag nodes on the canvas to rearrange the events and conditions of the journey. Data updates in real time as you make changes. 

[Nodes are connected](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) as an "eventual path," which means that visitors are counted as long as they eventually move from one node to the other, regardless of any events occurring between the two nodes. The time allotted for users to move along the path is determined by the container setting. 

![Journey canvas](assets/journey-canvas.png)

## Key features

Key features of the Journey canvas visualization include:

* Deep analysis of fallout and fallthrough that accommodates the most complex user journeys.

* A canvas for mapping and visualizing the various entry points, nodes, and paths of a user journey.

* Drag-and-drop interactions for adding components to the canvas and for repositioning existing nodes.

## Potential insights

Journey canvas provides actionable insights for the most complex journeys. 

### Path with the highest conversion rate {#conversion-rate-caption}

The most prominent insight in Journey canvas is shown as a caption at the top of the canvas itself. 

This caption summarizes which of all the paths in the journey had the highest conversion rate. 

When the journey contains multiple start nodes, the caption looks like this:

![Journey canvas insight caption](assets/journey-canvas-caption.png)

When the journey contains a single start node, the caption looks like this: 

![Journey canvas insight caption single start node](assets/journey-canvas-caption-singlestart.png)

Consider the following when interpreting this caption:

* A _path_ is defined as a start node that is connected by arrows to an end node, with any number of nodes connected between them. 

* The conversion rate calculation depends on the type of journey (the number of start nodes and end nodes contained in the journey, and whether the paths intersect between them).

  The following table describes how conversion rates are calculated based on the journey type:

  | Journey type | Conversion rate calculation | Example |
  |---------|----------|---------|
  | **A single start node and a single end node** | Conversion rate is calculated by dividing the number of the end node by that of the start node. | ![Journey with multiple starts that converge into a common node](assets/journey-canvas-single-path.png) |
  | **A single start node and multiple end nodes** | Conversion rate is calculated by finding the end node with the highest number, and dividing that number by that of the start node. | ![Journey with multiple starts that converge into a common node](assets/journey-canvas-singlestart-multiend.png) |
  | **Multiple standalone paths, with each path containing a single start node and a single end node** | Conversion rate is calculated by dividing the number of the end node by that of the start node. The path with the highest conversion rate is described in the caption. | ![Journey with multiple starts that converge into a common node](assets/journey-canvas-multi-start-separate.png) |
  | **Multiple start nodes that at any point in the journey converge into a common node** | Conversion rate is calculated by finding the end node with the highest number, and dividing that number by that of the start node with the lowest number. | ![Journey with multiple starts that converge into a common node](assets/journey-canvas-multi-start-converge.png) |

### Fallthrough, Fallout, and more

Following are a few examples of other insights Journey canvas can help provide. You can choose whether these insights are based on all people in the report suite, all people who started the journey, or all people from the previous node of the journey.

#### Fallthrough 

* The number and percentage of people who completed the journey (arrived at the ending node)

* The number and percentage of people who arrived at a given node of the journey

* The most common step that came after or before a given node of the journey

#### Fallout

* The nodes of the journey where people most commonly fell out of the journey (never arrived at any of the immediate next nodes)

#### Additional data for each node

* Add a breakdown dimension on any node of the journey to view additional data for that specific node

## Choose between Journey canvas, Fallout, or Flow visualizations

The Journey canvas visualization has similarities with the [Fallout visualization](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) and the [Flow visualization](/help/analysis-workspace/visualizations/c-flow/flow.md), but with important differences. 

### Understand the differences

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### When to use Journey canvas

Journey canvas is essential for:

* Fallout analysis involving journeys with multiple entry points and paths.

* Non-linear journeys with multiple entry points and paths, with a predefined sequence of pages.

* Exploratory, ad hoc analysis that is based on a predefined journey.

* Analysis that requires a primary metric other than Session, Person, or Occurrences.

Use [the table above](#understand-the-differences) to understand the differences between Journey canvas, Fallout, and Flow visualizations.

## Build analyses in Journey canvas

You can build analyses in Journey canvas that are based on any dimensions or metrics that are available in Analysis Workspace. For more information, see [Configure a Journey canvas visualization](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


>[!MORELIKETHIS]
>
> * [A Guide to Journey Canvas Visualization in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857)

