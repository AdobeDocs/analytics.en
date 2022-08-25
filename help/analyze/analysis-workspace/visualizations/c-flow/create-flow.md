---
description: Use the flow visualization in a Workspace project.
title: Configure a flow visualization
feature: Visualizations
role: User, Admin
exl-id: c2fdcc96-81ac-4d3b-b255-ff805b6ff0ea
---
# Configure a flow visualization

>[!NOTE]
>
>This new version of the [!UICONTROL Flow] visualization is currently in limited testing. 

The updated Flow visualization allows you to understand the journey stemming from or leading up to a specific conversion event on your website or your app. It traces a path through your dimensions (and dimension items) or metrics. Flow lets you configure the start or end of the path you are interested in, or analyze all those paths that flow through a dimension or dimension item. 

The new [!UICONTROL flow] experience enhances your workflow in several ways:

* You can now choose to start or end your path with the combination of a metric and a pathing dimension.
* It contains [!UICONTROL Advanced Settings] to let you further customize the [!UICONTROL flow].
* The new “Build” button saves time in analysis by allowing you to configure the journey all at once, then query, then automatically build out multiple columns and nodes at once​.

![new Flow UI](assets/new-flow.png)

## Configuration steps {#configure}

1. To start creating a flow diagram, add a blank panel to your project and click the visualizations icon in the left rail. Then drag the Flow visualization into the panel. Or drag the [!UICONTROL Flow] visualization into an existing project.

1. Anchor your Flow visualization using one of three options:

   * [!UICONTROL Starts with] (metrics, dimensions, or items), or
   * [!UICONTROL Contains] (dimensions, or items), or
   * [!UICONTROL Ends with] (metrics, dimensions, or items)

   Each of these categories is shown onscreen as a "drop zone." You can populate the drop zone in 3 ways:
   
   * Use the drop-down menu to select metrics or dimensions.
   * Drag items from the dimensions or metrics list.
   * Use search to find the metrics or dimension you are looking for.

   For example, let's assume that you want to trace everything that leads up to a checkout event. You would drag a checkout-related dimension or metric (such as [!UICONTROL Order exists]) into the **[!UICONTROL Ends with]** drop zone. 

1. If you choose a metric, you also need to provide a [!UICONTROL Pathing Dimension], as shown here, that you will use to build the path. The default is [!UICONTROL Page].

   ![pathing dimension](assets/pathing-dim.png) 
   
   >[!IMPORTANT]
   >
   >Calculated metrics cannot be dropped into the  **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** drop zones.

1. (Optional) Click **[!UICONTROL Show Advanced Settings]** to configure Advanced Settings:

   ![advanced settings](assets/adv-settings.png)

   | Setting | Description |
   | --- | --- |
   | **[!UICONTROL Wrap labels]** | Normally, the labels on the Flow elements are truncated to save screen real estate, but you can make the entire label visible by checking this box.  Default = unchecked. |
   | **[!UICONTROL Include repeat instances]** | Flow visualizations are based on instances of a dimension. This setting gives you the option to include or exclude repeated instances, e.g. Page reloads. However, repeats cannot be removed from Flow visualizations that include multi-valued dimensions, such as listVars, listProps, s.product, merchandising eVars, etc. Default = unchecked. |
   | **[!UICONTROL Limit to first/last occurrence]** | Limit paths to those that start/end with the first/last occurrence of a dimension/item/metric. See the section below entitled "Example scenario for 'limit to first/last occurrence'" for a more detailed explanation. |
   | **[!UICONTROL Number of Columns]** | Determines how many columns you want in your Flow diagram. |
   | **[!UICONTROL Items expanded per Column]** | How many items you want in each column. |
   | **[!UICONTROL Flow Container]** | <ul><li>Visit</li><li>Visitor</li></ul> Lets you switch between Visit and Visitor to analyze visitor pathing. These settings help you understand visitor engagement at the visitor level (across visits), or constrain the analysis to a single visit.  |

1. Click **[!UICONTROL Build]**.

## View and change the Flow output {#output}

![flow output](assets/flow-output.png)

A summary of the Flow configuration appears at the top of the diagram. The paths in the diagram are proportional. Paths with more activity appear thicker. 

To drill down further into the data, you have several options:

* The flow diagram is interactive. Mouse over the diagram to change the details that are shown.

* When you click on a node in the diagram, the details for that node appear. Click on the node again to collapse it.

   ![node-details](assets/node-details.png)

* You can filter a column to display only certain results, such as including and excluding, specifying criteria, etc.

* Click the plus sign (+) on the left to expand a column.

* Use the right-click options explained below to further customize the output.

* Click the pencil icon next to the configuration summary to further edit the flow or rebuild it with different options.

* You can also export and further analyze your Flow diagram as part of a project's .CSV file by going to **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**.

## Filtering

Above each column, a filter appears when you hover over it. By clicking the filter, you get the same filter dialog that exists in the Freeform table today. This filter works the same as it does in the Freeform table.

* Use advanced settings to include or exclude certain criteria with our list of operators. 
* Once you have filtered an item from the list, that specific column will reflect the filtering. (The filter either reduces it to only show the item allowed in the filter, or it removes all items except for the one item you want in the filter.
* All downstream and upstream columns should persist, as long as there is data flowing into the remaining nodes. 
* Once applied, the filter icon appears in blue above the column it is filtering. 
* To remove a filter, click on the filter icon to open the filter menu. Remove any filters applied and then click **[!UICONTROL Save]**. The flow should return to its previous, unfiltered state.

## Right-click options {#right-click}

| Option | Description |
|--- |--- |
| [!UICONTROL Focus on this node] | Change the focus to the selected node. The focus node appears at the center of the Flow diagram. |
| [!UICONTROL Start Over] | Returns you to the Freeform diagram builder, where you can build a new Flow diagram. |
| [!UICONTROL Create Segment from this point in flow] | Create a segment. This takes you into the Segment Builder, where you can configure the new segment. |
| [!UICONTROL Breakdown] | Break the node down by available Dimensions, Metrics, or Time. |
| [!UICONTROL Trend] | Create a trended diagram for the node. |
| [!UICONTROL Expand entire column] | Expand a column to show all nodes. By default, only the top five nodes display. |
| [!UICONTROL Collapse entire column] | Hide all nodes in a column. |
| [!UICONTROL Exclude Item]/[!UICONTROL Restore Excluded Items] | Removes a specific node from the column and automatically creates it as a filter at the top of the column. To restore the excluded item, right-click again and select **[!UICONTROL Restore Excluded Item]**. you can also open the filter at the top of the column and remove the pillbox with the item you just excluded. |

## Example scenario for 'limit to first/last occurrence'

When using this option, keep in mind that:

* **[!UICONTROL Limit to first/last occurrence]** counts only the first/last occurrence in the series. All other occurrences of the **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** criteria are discarded. 
* If used with a **[!UICONTROL Starts with]** flow, only the first occurrence that matches the start criteria is included. 
* If used with an **[!UICONTROL Ends with]** flow, only the last occurrence that matches the end criteria will be included. 
* The series used differs based on the container. If using the **[!UICONTROL Visit]** container, the series of hits will be the session. If using the **[!UICONTROL Visitor]** container, the series of hits will be all the hits for a given user in the provided date range. 
* The **[!UICONTROL Limit to first/last occurrence]** option can be configured in the advanced settings when using a Metric or Dimension Item in the “Starts with” or “Ends with” fields.
 
Example series of hits:

Home > Products > Add to cart > Products > Add to Cart > Billing > Order Confirmation
 
### Consider a flow analysis using the following settings:

* Start with[!UICONTROL  Add to cart] (Dimension Item)
* [!UICONTROL Page] pathing dimension
* [!UICONTROL Visit] container
 
If **[!UICONTROL Limit to first/last occurrence]** is *disabled*, then this single series of hits counts 2 occurrences of “Add to Cart”.
Expected Flow Output:
“Add to Cart” (2) —> “Products” (1)
                  -> “Billing” (1)
 
However, if **[!UICONTROL Limit to first/last occurrence]** is *enabled*, only the first occurrence of “Add to cart” is included in the analysis.
Expected Flow Output:
“Add to Cart” (1) —> “Products” (1)
 
### Consider the same series of hits but using the following settings:

* Ends with [!UICONTROL Add to cart] (Dimension Item)
* [!UICONTROL Page] pathing dimension
* [!UICONTROL Visit] container
 
If **[!UICONTROL Limit to first/last occurrence]** is *disabled*, then this single series of hits would count 2 occurrences of “Add to Cart”.
Expected Flow Output:
“Products” (2) <— “Add to cart” (2)
 
However, if **[!UICONTROL Limit to first/last occurrence]** is *enabled*, only the last occurrence of [!UICONTROL Add to cart] would be included in the analysis.
Expected Flow Output:
“Products” (1) <— “Add to cart” (1) 
