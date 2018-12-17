---
description: Learn about visualizations and visualization settings in Analysis Workspace.
keywords: Analysis Workspace
seo-description: Learn about visualizations and visualization settings in Analysis Workspace.
seo-title: Visualizations overview
solution: Analytics
title: Visualizations overview
topic: Reports and analytics
uuid: 318dea64-6277-4ec3-ad48-4dfcb7a54555
index: y
internal: n
snippet: y
---

# Visualizations overview

Learn about visualizations and visualization settings in Analysis Workspace.

## Visualizations panel {#section_DC07F032FBEF4046A40F7B95C28DA018}

To display the Visualizations panel, click **[!UICONTROL Visualizations]** in the side panel.

![Step Result](assets/visualizations.png)

Most visualization types (such as Area, Bar, Donut, and Line charts) will be familiar to you if you use Adobe Analytics. However, Analysis Workspace provides visualization settings and many new or unique visualizations types with interactive capabilities.

## Visualization settings {#section_D3BB5042A92245D8BF6BCF072C66624B}

To access [!UICONTROL Visualization Settings], drag a visualization to the [!UICONTROL Freeform Panel], then click the [!UICONTROL Visualization Settings] gear icon.

>[!IMPORTANT]
>
>Which visualization settings are visible depends on the visualization. Not all settings apply to all visualizations. In addition, some advanced settings appear **only** for specific visualizations, such as the [Histogram settings](../../analyze/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477).

![](assets/visualization_settings.png)

<table id="table_E0695243886046979EE609FAE5D6EA00"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Percentages </p> </td> 
   <td colname="col2"> <p>Displays values in percentages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>100% Stacked </p> </td> 
   <td colname="col2"> <p>This setting on area stacked or bar stacked or horizontal bar stacked visualizations turns the chart into a "100% stacked" visualization. Example: </p> <p><img href="assets/stacked_100_percent.png" align="left" placement="break" width="400px" id="image_1B60D53F7EB84571B1580BC3A1E603EE" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Legend Visible </p> </td> 
   <td colname="col2"> <p>Lets you hide the filter details text for the Summary Number/Summary Change visualization. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limit Max Items </p> </td> 
   <td colname="col2"> <p>Lets you limit the number of items that a visualization displays. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anchor Y Axis at Zero </p> </td> 
   <td colname="col2"> <p> If all the values plotted on the chart are considerably above zero, the chart default will make the bottom of the y-axis NON-ZERO. If you check this box, the y-axis will be forced to zero (and it will re-draw the chart). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Normalization </p> </td> 
   <td colname="col2"> <p>Forces metrics to equal proportions. See <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=normalization" format="https" scope="external"> Normalization</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Display Dual Axis </p> </td> 
   <td colname="col2"> <p>Only applies if you have two metrics - you can have a y-axis on the left (for one metric) and on the right (for the other metric). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Show Anomalies </p> </td> 
   <td colname="col2"> <p>Enhances line graphs and freeform tables to display data anomalies. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Create Visual icon {#section_9C11D9DEDC42413AA53E69A71A509DFC}

If you are not sure which visualization to pick, click the **[!UICONTROL Create Visual]** icon in any table row. This icon will appear when you hover over the table row. Clicking it prompts Analysis Workspace to take an educated guess at which visualization would best fit your data. For example, if you have up to 3 segments selected, it will create a Venn diagram. For more than 3 segments, it will create a bar chart. For other types of data, it might create a line graph, etc.

![](assets/create-visual.png)

## Right-click visualization/panel menu {#section_05B7914D4C9E443F97E2BFFDEC70240C}

Settings that are contextual to a graph can be accessed when right-clicking next to a visualization or panel header. Some or all of the following settings will be available:

![](assets/right-click_menu.png)

| Setting | Description |
|--- |--- |
|Insert Copied Visualization/Panel|Lets you paste ("insert") that copied element into another place within the project, or into a completely different project.|
|Copy Visualization/Panel|Lets you right-click and copy a visualization or panel.|
|Duplicate Visualization/Panel|Makes an exact duplicate of the current visualization, which you can then modify.|
|Collapse all Panels|Collapses all project panels.|
|Collapse all Visualizations in Panel|Collapses all visualizations in this project panel.|
|Expand all Panels|Expands all project panels.|
|Expand all Visualizations in Panel|Expands all visualizations in this project panel.|
|Edit Description|Add (or edit) a text description for the visualization/panel. This description appears in  Project  >  Project Info & Settings .|
|Get Panel Link|Lets you direct someone to a specific panel within a project.|
|Get Visualization Link|Lets you copy and share this link to send others directly to this visualization. Users will be required to log in.|
|Start Over|(Works for Flow, Venn, Histogram) Deletes the configuration for the current visualization and opens a new panel where you can re-configure it.|

## Edit legend labels {#section_94F1988CB4B9434BA1D9C6034062C3DE}

You can rename series names in visualization legends (Fallout, Area, Area Stacked, Bar, Bar Stacked, Donut, Histogram, Horizontal Bar, Horizontal Bar Stacked, Line, Scatter, and Venn) to help you make visuals more consumable.

Legend editing does **not** apply to: Treemap, Bullet, Summary Change or Number, Text, Freeform, Histogram, Cohort or Flow visualizations.

To edit a legend label in a Line chart, for example,

1. Right-click one of the legend labels. 
1. Click **[!UICONTROL Edit Label]**.

   ![](assets/edit-label.png)

1. Enter the new label text. 
1. Press **[!UICONTROL Enter]** to save.

Here is a [link to a video](https://www.youtube.com/watch?v=mry3vDrTml0&index=61&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) on this topic. 
