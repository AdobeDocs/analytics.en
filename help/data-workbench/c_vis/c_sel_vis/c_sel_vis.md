---
description: Selecting elements within a visualization dynamically filters the dataset.
seo-description: Selecting elements within a visualization dynamically filters the dataset.
seo-title: Make selections in visualizations
solution: Analytics
title: Make selections in visualizations
topic: Data workbench
uuid: 40e7fabe-89f4-49c2-a435-1c5420590761
index: y
internal: n
snippet: y
---

# Make selections in visualizations

Selecting elements within a visualization dynamically filters the dataset.

 When you make a selection in a visualization, all of the other visualizations in the workspace automatically update to reflect the data associated with only those elements that you have selected.

The following workspace shows a Movie table in which the movie *Cocktail* is selected. In the workspace, the Score table and the metric legend automatically filter their displays for the selected element (that is, their displays reflect the data for the movie *Cocktail*).

![](assets/wsp_selection_Basic.png)

As shown in the example above, when a selection is made, a glow appears around the visualization and the non-selected elements within that visualization dim. To facilitate comparisons with the complete dataset, narrow white lines referred to as benchmarks appear in the bar graph to mark the shape of the original, unfiltered data. For more information about benchmarks, see [Understanding Benchmarks](../../c_vis/c_ustd_benchmks.md#concept_C7B0F4102E92458096F8C4765CBE2914).

**To make a selection**

You can make selections in any visualization that displays at least one dimension except scatter plots and legends.

Use the following mouse and key sequences to select the desired element(s):

|  To...  | Use this sequence...  |
|---|---|
|  Select a single element  | Click  |
|  Select a range of elements  | Click+drag  |
|  Add an element to current selection  | Ctrl+click  |
|  Clear a single selection  | Shift+click  |
|  Clear all selections (that is, re-select all elements)  | Right-click any value in the visualization  |

**To clear a selection**

Use the following mouse and key sequences to clear a selection:

|  To  | Use this sequence...  |
|---|---|
|  Clear a single selection  | Shift+click  |
|  Clear all selections (that is, re-select all elements)  | Right-click any value in the visualization  |

