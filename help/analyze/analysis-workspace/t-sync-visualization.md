---
description: Synchronizing visualizations lets you control which data table or data source corresponds to a visualization.
keywords: Analysis Workspace;Synchronize visualization with data source
seo-description: Synchronizing visualizations lets you control which data table or data source corresponds to a visualization.
seo-title: Manage data sources
solution: Analytics
title: Manage data sources
topic: Reports and analytics
uuid: a755af65-8fad-4803-aad9-420951e5b7f3
index: y
internal: n
snippet: y
---

# Manage data sources

Synchronizing visualizations lets you control which data table or data source corresponds to a visualization.

 **Tip:** You can tell which visualizations are related by the color of the dot next to the title. Matching colors mean that visualizations are based on the same data source.

Managing a data source lets you show the data source or lock the selection. These settings determine how the visualization changes (or doesn't change) when new data comes in. 

1. [Create a project](../../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md#task_C2C698ACC7954062A28E4784911E6CF2) with a data table and a [visualization](../../../analyze/analysis-workspace//freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276).
1. In the data table, select the cells (data source) you want to associate with the visualization.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Select **[!UICONTROL Show Data Source]** or **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synchronizing a visualization to a table cell creates a new (hidden) table and color-codes the synchronized visualization with that table. 

<table id="table_ED9C1142DD474140830C43466E825C4B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Linked Visualizations </p> </td> 
   <td colname="col2"> <p>If there are visualizations connected to a freeform or cohort table, the top left dot opens to list the connected visualizations and have a "show" checkbox option to show/hide the table. </p> <p>Hovering highlights the linked visualization, and clicking it takes you to it. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Show Data Source </p> </td> 
   <td colname="col2"> <p>Lets you show (by enabling the checkbox) or hide (by disabling) the data table that corresponds to the visualization. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lock Selection </p> </td> 
   <td colname="col2"> <p>Enable this setting to lock the visualization to the data currently selected in the corresponding data table. Once enabled, choose between: </p> <p><b>Selected Positions</b>: Choose this option if you want the visualization to stay locked on the positions that are selected in the corresponding data table. These positions will continue to be visualized, even if the specific items in these positions change. For example, choose this option if you want to show the top five campaign names in this visualization at all times, no matter which campaign names show up in the top five. </p> <p><b>Selected Items</b>: Choose this option if you want the visualization to stay locked on the specific items currently selected in the corresponding data table. These items will continue to be visualized, even if they change their ranking among items in the table. For example, choose this option if you want to show the same five specific campaign names in this visualization at all times, no matter where those campaign names rank. </p> </td> 
  </tr> 
 </tbody> 
</table>

>This new architecture, introduced in July 2017, differs from the previous one in that Analysis Workspace no longer creates a duplicate hidden table that stores the locked selection for you. Now, the data source points to the table that you created the visualization from. 
>
>**Example use cases:** 
>
>* You can create a summary visualization and lock it to a cell in the table you created it from. When you enable "Show Data Source", it shows you exactly where this information is coming from in the table. The source data will be greyed out: 
>
>  ![](assets/data-source2.png)>
>* You can add lots of visualizations and source them from different cells in the same table, as shown here. The table is the same as in the example above, but the sourced cell (and metric) is different: 
>
>  ![](assets/data-source3.png)>
>* You can see whether there are visualizations connected to a freeform or cohort table by clicking the top left dot (Data Source Settings). Hovering will highlight the linked visualization, and clicking it will take you to it. 
>
>  ![](assets/linked-visualizations.png)>
