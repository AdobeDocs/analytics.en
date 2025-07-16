---
description: Learn how to configure the flow visualization in Analysis Workspace
title: Configure A Flow Visualization
feature: Visualizations
role: User, Admin
exl-id: c2fdcc96-81ac-4d3b-b255-ff805b6ff0ea
---
# Configure a flow visualization {#configure-a-flow-visualization}

>[!CONTEXTUALHELP]
>id="workspace_flow_startswith"
>title="Starts with"
>abstract="This field can only be set on the initial build. To update this field, select **[!UICONTROL Reset]** to build a new Flow visualization."

>[!CONTEXTUALHELP]
>id="workspace_flow_contains"
>title="Contains"
>abstract="This field can only be set on the initial build. To update this field, select **[!UICONTROL Reset]** to build a new Flow visualization."

>[!CONTEXTUALHELP]
>id="workspace_flow_endswith"
>title="Ends with"
>abstract="This field can only be set on the initial build. To update this field, select **[!UICONTROL Reset]** to build a new Flow visualization."

>[!CONTEXTUALHELP]
>id="workspace_flow_pathingdimension"
>title="Pathing dimension"
>abstract="Select a dimension to use as your path leading to or going from your selected component."

>[!CONTEXTUALHELP]
>id="workspace_flow_container"
>title="Flow container"
>abstract="Select the container to use to display (numbers for) the pathing."

>[!CONTEXTUALHELP]
>id="workspace_flow_include_repeats_disabled"
>title="Include repeats (disabled)"
>abstract="Repeats cannot be removed from Flow visualizations that include multi-valued dimensions."

>[!CONTEXTUALHELP]
>id="workspace_flow_include_repeats_default"
>title="Include repeats"
>abstract="Flow visualizations are based on instances of a dimension. This setting gives you the option to include or exclude repeated instances, For example: Page reloads."

>[!CONTEXTUALHELP]
>id="workspace_flow_limit_occurrence"
>title="Limit to first/last occurrence"
>abstract="Results are limited to paths when the first/last touchpoint is an entry/exit."

>[!CONTEXTUALHELP]
>id="workspace_flow_numberofcolumns"
>title="Number of columns"
>abstract="This field can only be set on the initial build. To update this field, select **[!UICONTROL Reset]** to build a new Flow visualization."

>[!CONTEXTUALHELP]
>id="workspace_flow_itemsexpandedpercolumn"
>title="Items expanded per column"
>abstract="This field can only be set on the initial build. To update this field, select **[!UICONTROL Reset]** to build a new Flow visualization."

>[!CONTEXTUALHELP]
>id="workspace_flow_resettoupdate"
>title="Reset to update"
>abstract="This field can only be set on the initial build. To update this field, select **[!UICONTROL Reset]** to build a new Flow visualization."


Flow visualizations help you understand the journey originating from a specific conversion event on your website or your app. Or leading up to a specific conversion event. The visualization traces a path through your dimensions (and dimension items) or metrics. 

You can configure the start or end of the path you are interested in. Or analyze all paths that flow through a dimension or dimension item.
![new Flow UI](assets/new-flow.png)

## Use

1. Add a ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flow]** visualization. See [Add a visualization to a panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Anchor your Flow visualization using one of the following options:

   * [!UICONTROL **Starts with**] (metrics, dimensions, or items), or
   * [!UICONTROL **Contains**] (dimensions, or items), or
   * [!UICONTROL **Ends with**] (metrics, dimensions, or items)

   Each of these categories is shown onscreen as a *drop zone*. You can populate the drop zone in 3 ways:

   * Use the drop-down menu to select metrics or dimensions.
   * Drag dimensions or metrics from the left panel.
   * Begin typing the name of a dimension or metric, then select it when it appears in the drop-down list.

   >[!IMPORTANT]
   >
   >Calculated metrics cannot be used in the **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** fields.

1. If you choose a metric, you also need to provide a [!UICONTROL **Pathing Dimension**] to use as your path leading to or coming from your selected component, as shown here. The default is [!UICONTROL **Page**].

   ![Flow configuration](assets/flow-configure.png) 

1. (Optional) Select **[!UICONTROL Show advanced settings]** to configure any of the following options:


   | Setting | Description |
   | --- | --- |
   | **[!UICONTROL Wrap labels]** | Normally, the labels on the Flow elements are truncated to save screen real estate, but you can make the entire label visible by checking this box.  Default = unchecked. |
   | **[!UICONTROL Include repeat instances]** | Flow visualizations are based on instances of a dimension. This setting gives you the option to include or exclude repeated instances, for example, Page reloads. However, repeats cannot be removed from Flow visualizations that include multi-valued dimensions, such as listVars, listProps, s.product, merchandising eVars, etc. <p>This option is disabled by default.</p> |
   | **[!UICONTROL Limit to first/last occurrence]** | Limit paths to paths that start or end with the first or last occurrence of a dimension, item, or metric. See [Limit to first/last occurrence](#example-scenario-for-limit-to-firstlast-occurrence) for a more detailed explanation. |
   | **[!UICONTROL Number of columns]** | The number of columns you want in your Flow diagram. You can specify a maximum of 5 columns. |
   | **[!UICONTROL Items expanded per column]** | The number of items you want in each column. You can specify a maximum of 10 items expanded per column. |
   | **[!UICONTROL Flow container]** | You can switch between **[!UICONTROL Visit]** and **[!UICONTROL Visitor]** to analyze pathing. These settings help you understand a visitor's engagement at the visitor level (across visits), or constrain the analysis to a single visit.  |

   >[!IMPORTANT]
   >
   >The combination of **[!UICONTROL Number of columns]** and **[!UICONTROL Items expanded per column]** determine the number of underlying requests required to create the flow visualization. The higher those numbers, the longer it takes to render a visualization.


1. Select **[!UICONTROL Build]**.


### Example 

Suppose that you want to trace the path that users took both to and from the most popular pages on your site.

1. Create a flow visualization as described above.
1. Drag the [!UICONTROL **Page**] dimension into the **[!UICONTROL Contains]** field, then select [!UICONTROL **Build**].
1. The Flow visualization builds, with the most-viewed page visible in the focus node, at the center of the visualization. You also see the top pages leading into that page (to the left of the focus node) as well as the top pages leading out of that page (to the right of the focus node).
1. Analyze data in the flow, as described in [Configure](#configure).


## Configure

A summary of the Flow configuration appears at the top of the visualizations. The paths in the diagram are proportional. Paths with more activity appear thicker. 

![Flow output example showing Ends with Visits, Pathing dimension: Page, and Flow container: Vistors.](assets/flow-output.png)

To drill down further into the data, you have several options:

* The flow diagram is interactive. Mouse over the diagram to change the details that are shown.

* When you select a node in the diagram, the details for that node appear. Select the node again to collapse it.

  Leaving multiple nodes expanded in a flow visualization can affect reporting time. As a general guideline, no more than 10 nodes should remain expanded at a given time. 

   ![Example interactive flow diagram showing node-details.](assets/node-details.png)

* You can filter a column to display only certain results, such as including and excluding, specifying criteria, etc.

* Select ![AddCircle](/help/assets/icons/AddCircle.svg) on the left or right side to expand a column.

* To customize the output, use the [context menu](#context-menu) options.

* To edit the flow or rebuild it with different options, select ![Edit](/help/assets/icons/Edit.svg) next to the configuration summary.

## Filter

Above each column, a filter ![Filter](/help/assets/icons/Filter.svg) appears when you hover over it. By selecting the filter, you get the same filter dialog that exists in the Freeform table. See [Filter and sort](freeform-table/../../freeform-table/filter-and-sort.md).

* Use **[!UICONTROL Show advanced]** to configure advanced settings to include or exclude certain criteria with a list of operators. See [Filters and sort](../freeform-table/filter-and-sort.md) for more information.
* Once you have filtered a column, that specific column reflects the filtering. A blue ![Filter](/help/assets/icons/FilterColored.svg) indicates that the column is filtered.  The filter either reduces the column to show only the item allowed in the filter. Or it removes all items, except for the one item you want in the filter.
* All downstream and upstream columns persist, as long as there is data flowing into the remaining nodes. 
* To remove a filter, select ![Filter](/help/assets/icons/Filter.svg) to open the filter menu. Remove any filters applied and then select **[!UICONTROL Save]**. The flow should return to its previous, unfiltered state.

## Context menu

Use a context menu on any node in the flow visualization with the following options:

| Option | Description |
|--- |--- |
| **[!UICONTROL Focus on this node]** | Change the focus to the selected node. The focus node appears at the center of the Flow diagram. |
| **[!UICONTROL Start over]** | Return you to the Freeform diagram builder, where you can build a new Flow diagram. |
| **[!UICONTROL Create a filter for this path]** | Create a filter. This selection takes you into the Filter builder, where you can configure the new filter. |
| **[!UICONTROL Breakdown]** | Break the node down by available Dimensions, Metrics, or Time. |
| **[!UICONTROL Filter column]** | The same filter options appear as are available in the Freeform table. For more information about the available options, see the section "Apply a simple or advanced filter to a table" in [Filter and sort tables](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).|
| **[!UICONTROL Exclude item]** or **[!UICONTROL Restore excluded items]** | Removes a specific node from the column and automatically creates it as a filter at the top of the column. To restore the excluded item, from the context menu select **[!UICONTROL Restore Excluded Item]**. you can also open the filter at the top of the column and remove the pillbox with the item you just excluded. |
| **[!UICONTROL Trend]** | Create a trended diagram for the node. |
| **[!UICONTROL Show next column]** / **[!UICONTROL Show previous column]** | Reveals the next (right) or previous (left) column of the visualization. |
| **[!UICONTROL Hide colum]**n | Hides the selected column from the visualization. | 
| **[!UICONTROL Expand entire column]** | Expand a column to show all nodes. By default, only the top five nodes display. |
| **[!UICONTROL Create audience from selection]** | Creates an audience based on the column that is selected. |
| **[!UICONTROL Collapse entire column]** | Hide all nodes in a column. |

## Limit to first/last occurrence

When using this option, keep in mind that:

* **[!UICONTROL Limit to first/last occurrence]** counts only the first/last occurrence in the series. All other occurrences of the **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** criteria are discarded. 
* If used with a **[!UICONTROL Starts with]** flow, only the first occurrence that matches the start criteria is included. 
  In the example below, **all** occurrences of *Add to cart* and *Product main category* in each step of the flow are included.
  ![No limit, first](assets/limitofffirst.png)

  In the example below, only the **first** occurrences of *Add to cart* and *Product main category* in each step of the flow are included.
  ![Lint, start](assets/limitonfirst.png)
* If used with an **[!UICONTROL Ends with]** flow, only the last occurrence that matches the end criteria is included. 
  In the example below, **all** occurrences of *Product main category* and *Add to cart* in each step of the flow are included.
  ![No limit, first](assets/limitofflast.png)

  In the example below, only the **last** occurrences of *Product main category* and *Add to cart* in each step of the flow are included.
  ![Lint, start](assets/limitonlast.png)
* The series used differs based on the container. If using the **[!UICONTROL Visitor]** container, the series of events are the visits. If using the **[!UICONTROL Visitor]** container, the series of events are all the hits for a given user in the provided date range. 
* The **[!UICONTROL Limit to first/last occurrence]** option can be configured in the advanced settings when using a Metric or Dimension Item in the **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** fields.


>[!MORELIKETHIS]
>
>[Add a visualization to a panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualization settings](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Visualization context menu](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>


<!--
## Create a flow visualization {#configure}

1. Add a blank panel to your project and click the visualizations icon in the left rail. 

   Or
   
   Add a visualization in any of the ways described in the "Add visualizations to a panel" section in [Visualizations overview](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Anchor your Flow visualization using one of the following options:

   * [!UICONTROL **Starts with**] (metrics, dimensions, or items), or
   * [!UICONTROL **Contains**] (dimensions, or items), or
   * [!UICONTROL **Ends with**] (metrics, dimensions, or items)

   Each of these categories is shown onscreen as a "drop zone." You can populate the drop zone in 3 ways:

   * Use the drop-down menu to select metrics or dimensions.
   * Drag dimensions or metrics from the left rail.
   * Begin typing the name of a dimension or metric, then select it when it appears in the drop-down list.

   >[!IMPORTANT]
   >
   >Calculated metrics cannot be used in the  **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** fields.

1. If you choose a metric, you also need to provide a [!UICONTROL **Pathing Dimension**] to use as your path leading to or coming from your selected component, as shown here. The default is [!UICONTROL **Page**].

   ![pathing dimension](assets/pathing-dim.png)

1. (Optional) Select **[!UICONTROL Show advanced settings]** to configure any of the following options:

   ![advanced settings](assets/adv-settings.png)

   | Setting | Description |
   | --- | --- |
   | **[!UICONTROL Wrap labels]** | Normally, the labels on the Flow elements are truncated to save screen real estate, but you can make the entire label visible by checking this box.  Default = unchecked. |
   | **[!UICONTROL Include repeat instances]** | Flow visualizations are based on instances of a dimension. This setting gives you the option to include or exclude repeated instances, e.g. Page reloads. However, repeats cannot be removed from Flow visualizations that include multi-valued dimensions, such as listVars, listProps, s.product, merchandising eVars, etc. <p>This option is disabled by default.</p> |
   | **[!UICONTROL Limit to first/last occurrence]** | Limit paths to those that start/end with the first/last occurrence of a dimension/item/metric. See the section below, [Example scenario for 'limit to first/last occurrence'](#example-scenario-for-limit-to-firstlast-occurrence), for a more detailed explanation. |
   | **[!UICONTROL Number of columns]** | The number of columns you want in your Flow diagram. You can specify a maximum of 5 columns. |
   | **[!UICONTROL Items expanded per column]** | The number of items you want in each column. You can specify a maximum of 10 items expanded per column.  |
   | **[!UICONTROL Flow container]** | <ul><li>Visit</li><li>Visitor</li></ul> Lets you switch between Visit and Visitor to analyze visitor pathing. These settings help you understand visitor engagement at the visitor level (across visits), or constrain the analysis to a single visit.|

   >[!IMPORTANT]
   >
   >The combination of **[!UICONTROL Number of columns]** and **[!UICONTROL Items expanded per column]** determine the number of underlying requests required to create the flow visualization. The higher those numbers, the longer it takes to render a visualization.

1. Select **[!UICONTROL Build]**.

>[!INFO]
>
>**Example:** Suppose that you want to trace the path that users took both to and from the most popular pages on your site.
>
>To do this, you would
> 
>1. Begin creating a flow visualization as described above.
>1. Drag the [!UICONTROL **Page**] dimension into the **[!UICONTROL Contains]** field, then select [!UICONTROL **Build**].
>1. The Flow visualization builds with the most-viewed page visible in the focus node in the center of the visualization. You also see the top pages leading into that page (to the left of the focus node) as well as the top pages leading out of that page (to the right of the focus node).
>1. Analyze data in the flow, as described in [View and change the Flow output](#view-and-change-the-flow-output).


## View and change the Flow output {#output}

![flow output](assets/flow-output.png)

A summary of the Flow configuration appears at the top of the diagram. The thickness of a path in the diagram is proportional to its activity, with paths with more activity appearing thicker than those with less activity.

To drill down further into the data, you have several options:

* The flow diagram is interactive. Mouse over the diagram to change the details that are shown.

* When you select on a node in the diagram, the details for that node appear. Select on the node again to collapse it.

   ![node-details](assets/node-details.png)

* You can filter a column to display only certain results, such as including and excluding, specifying criteria, and so forth.

* Select the plus sign (+) on the left to expand a column.

* Use the right-click options explained below to further customize the output.

* Select the pencil icon next to the configuration summary to further edit the flow or rebuild it with different options.

* You can also export and further analyze your Flow diagram as part of a project's .CSV file by going to **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**.

## Filtering

Above each column, a filter appears when you hover over it. By selecting the filter, you get the same filter dialog that exists in the Freeform table today. This filter works the same as it does in the Freeform table.

* Use advanced settings to include or exclude certain criteria with our list of operators.
* Once you have filtered an item from the list, that specific column will reflect the filtering. (The filter either reduces it to only show the item allowed in the filter, or it removes all items except for the one item you want in the filter.
* All downstream and upstream columns should persist, as long as there is data flowing into the remaining nodes.
* Once applied, the filter icon appears in blue above the column it is filtering.
* To remove a filter, select the filter icon to open the filter menu. Remove any filters applied and then select **[!UICONTROL Save]**. The flow should return to its previous, unfiltered state.

## Right-click options {#right-click}

| Option | Description |
|--- |--- |
| [!UICONTROL Start over] | Returns you to the Freeform diagram builder, where you can build a new Flow diagram. |
| [!UICONTROL Create segment for this path] | Create a segment. This takes you into the Segment Builder, where you can configure the new segment. |
| [!UICONTROL Breakdown] | Break the node down by available Dimensions, Metrics, or Time. |
| [!UICONTROL Trend] | Create a trended diagram for the node. |
| Show next column / Show previous column | Reveals the next (right) or previous (left) column of the visualization. |
| Hide column | Hides the selected column from the visualization. | 
| [!UICONTROL Expand entire column] | Expand a column to show all nodes. By default, only the top five nodes display. |

## Example scenario for 'limit to first/last occurrence'

When using this option, keep in mind that:

* **[!UICONTROL Limit to first/last occurrence]** counts only the first/last occurrence in the series. All other occurrences of the **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** criteria are discarded.
* If used with a **[!UICONTROL Starts with]** flow, only the first occurrence that matches the start criteria is included.
* If used with an **[!UICONTROL Ends with]** flow, only the last occurrence that matches the end criteria will be included.
* The series used differs based on the container. If using the **[!UICONTROL Visit]** container, the series of hits will be the session. If using the **[!UICONTROL Visitor]** container, the series of hits will be all the hits for a given user in the provided date range.
* The **[!UICONTROL Limit to first/last occurrence]** option can be configured in the advanced settings when using a Metric or Dimension Item in the "Starts with" or "Ends with" fields.

Example series of hits:

Home > Products > Add to cart > Products > Add to Cart > Billing > Order Confirmation

### Consider a flow analysis using the following settings:

* Start with[!UICONTROL  Add to cart] (Dimension Item)
* [!UICONTROL Page] pathing dimension
* [!UICONTROL Visit] container

If **[!UICONTROL Limit to first/last occurrence]** is *disabled*, then this single series of hits counts 2 occurrences of "Add to Cart".
Expected Flow Output:
"Add to Cart" (2) —> "Products" (1)
                  -> "Billing" (1)

However, if **[!UICONTROL Limit to first/last occurrence]** is *enabled*, only the first occurrence of "Add to cart" is included in the analysis.
Expected Flow Output:
"Add to Cart" (1) —> "Products" (1)

### Consider the same series of hits but using the following settings:

* Ends with [!UICONTROL Add to cart] (Dimension Item)
* [!UICONTROL Page] pathing dimension
* [!UICONTROL Visit] container

If **[!UICONTROL Limit to first/last occurrence]** is *disabled*, then this single series of hits would count 2 occurrences of "Add to Cart".
Expected Flow Output:
"Products" (2) <— "Add to cart" (2)

However, if **[!UICONTROL Limit to first/last occurrence]** is *enabled*, only the last occurrence of [!UICONTROL Add to cart] would be included in the analysis.
Expected Flow Output:
"Products" (1) <— "Add to cart" (1)

-->