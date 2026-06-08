---
description: Learn how to use the Journey canvas visualization in Analysis Workspace to analyze user journeys, fallout, and multi-path conversions.
title: Journey Canvas Troubleshooting
feature: Visualizations
role: User, Admin
---
# Journey canvas troubleshooting

>[!BEGINSHADEBOX]

_This article documents the Journey canvas visualization in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**.<br/><br/>_See [Journey canvas overview](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas-troubleshooting) for the_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** version of this article._

>[!ENDSHADEBOX]

The Journey canvas visualization allows you to analyze and gain deep insights on the journeys that you provide to your users and customers. 

To learn more about Journey canvas, see [Journey canvas overview](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) and [Configure a Journey canvas visualization](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

The following information can help you troubleshoot unintended outcomes you might be seeing, such as nodes that come later in the journey that show a higher percentage or number count than nodes that come earlier in the journey.

## Nodes with a higher percentage or value than previous nodes 

It is possible in Journey canvas for nodes that come later in the journey to show a higher percentage or number count than nodes that come earlier in the journey. 

In other words, unlike in Fallout visualizations, which are always funnel-shaped (with participation decreasing with each step), Journey canvas visualizations can have higher participation in later steps of the journey than in previous steps. 

This can occur in the following scenarios:

* When using a primary metric other than People or Sessions

* When multiple paths converge into a single node

### The journey uses a primary metric other than People or Sessions

Because Journey canvas allows you to use any metric as the primary metric, this can result in nodes that come later in the journey to show a higher percentage or number count than nodes that come earlier in the journey.

![Journey with nodes with a higher percentage than previous node](assets/journey-canvas-higher-percentage.png)

The journey used in the following scenarios is configured with these settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 1: User A follows the journey path in the first session. In a subsequent session, the user has an event that matches only a later node.

Suppose that User A visits the site and completes the journey (Node 1: "Visit site" > Node 2: "View Product A" > Node 3: "Check out"). Because User A had an event that matched each node of the journey in order, an event is counted on each node of the journey. 

Now, suppose that User A visits the site again in a later session. Because User A already completed the journey in a previous session by following the journey path, this means that any time User A has an event that matches any node in the journey--even if User A has not followed the path of the journey in their current session--an event is counted on the relevant node in the journey. For example, if User A checks out, then an event is counted on the "Check out" node. This can result in a higher percentage and number on the "Check out" node than on the preceding node, "View Product A."

In this example, the journey's container setting of "Person" plays a critical role in determining that the event on the third node ("Check out") is counted in the subsequent session. 

Alternatively, if the container setting had been set to "Session," then the event that took place only on the third node in the subsequent visit would not have counted in the journey, because the statistics shown in the journey would be constrained to a single defined session for a given person. To learn more about the container setting, see [Begin building a Journey canvas visualization](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization) in the article [Configure a Journey canvas visualization](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### Scenario 2: User B falls out of the journey

Suppose that User B visits the site and does not complete the journey (visits the site, views Product B, and then checks out). In this case, an event is counted for the journey's start node, "Visit site," but an event is not counted for the remaining nodes, and User B falls out of the journey. Even though User B checked out, an event is not counted on the third node ("Check out") because User B did not complete the journey by viewing Product A prior to checking out. 

This is because events are counted for each node only when people follow the journey's "eventual path." This means that events are counted only if the person eventually moved from one node to the other, regardless of any events occurring between the two nodes. 

### The journey has multiple paths converging into a single node

Journey canvas allows you to include multiple start nodes in a single journey, resulting in multiple paths. These paths can converge into a common node, resulting in nodes that come later in the journey showing a higher percentage or number count than nodes that come earlier in the journey.

![A journey with multiple paths converging into a single node](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### Journey percentages

While the numbers shown on each node of a journey remain constant regardless of what is selected in the **[!UICONTROL Percentage value]** field, the percentages themselves can change. 

The following sections show how the percentages can change for the same journey, depending on which of the following options is selected in the **[!UICONTROL Percentage value]** field:

+++Percent of start node

The nodes in this journey contain the following statistics when the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of start node]**:

![Journey with nodes with a higher percentage than previous node](assets/journey-canvas-higher-percentage.png)

|Node | Statistics |
|---------|----------|
| Node 1 - "Visit site" | In this journey, there were 354,147 events on the site within the reporting date range, as shown in the journey's start node, "Visit site."  |
| Node 2 - "View Product A" | Of the total number of events shown in the start node, 14% (48,394) of them matched the criteria of the journey's second node, "View Product A."  |
| Node 3 - "Check out" | Of the total number of events shown in the start node, 32% (113,782) of them matched the criteria of the journey's third node, "Check out."  |

+++

+++Percent of previous node

The nodes in this journey contain the following statistics when the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of previous node]**:

![Journey with nodes with a higher percentage than previous node](assets/journey-canvas-percentage-previous.png)

|Node | Statistics |
|---------|----------|
| Node 1 - "Visit site" | In this journey, there were 354,147 events on the site within the reporting date range, as shown in the journey's start node, "Visit site."  |
| Node 2 - "View Product A" | Of the total number of events shown in the previous node, 14% (48,394) of them matched the criteria of the journey's second node, "View Product A."  |
| Node 3 - "Check out" | Of the total number of events shown in the previous node, greater than 100% (113,782) of them matched the criteria of the journey's third node, "Check out."  |

+++

+++Percent of total

The nodes in this journey contain the following statistics when the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]**:

![Journey with nodes with a higher percentage than previous node](assets/journey-canvas-percentage-total.png)

|Node | Statistics |
|---------|----------|
| Node 1 - "Visit site" | In this journey, there were 354,147 events on the site within the reporting date range, as shown in the journey's start node, "Visit site."  |
| Node 2 - "View Product A" | Of the total number of events, less than 1% (48,394) of them matched the criteria of the journey's second node, "View Product A."  |
| Node 3 - "Check out" | Of the total number of events, 1% (113,782) of them matched the criteria of the journey's third node, "Check out."  |

+++

## Compatibility between the container metric and the primary metric

You can configure the Journey canvas container to be Person (which uses the People metric) or Session (which uses the Sessions metric).

Make sure you choose a primary metric that is compatible with the container metric that is currently selected. Most metrics are compatible with the container metrics that are available. However, some combinations of container metrics and primary metrics should be avoided.

For example, using Person as the container with Session as the primary metric can result in unintended outcomes.

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
