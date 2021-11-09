---
description: Use the map visualization in a Workspace project.
title: Map
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
---
# Map

## Overview {#section_19F740FAF08D47B1AF1EF239A74FC75C}

The Map Visualization in Analysis Workspace

* Lets you build a visual map of any metric (including calculated metrics).
* Is useful for identifying and comparing metric data across different geographic regions.
* Can support 2 data sources: latitude/longitude from mobile usage or geographic dimension for web usage.
* Supports PDF export.
* Leverages WebGL for graphics display. If your graphics drivers do not support WebGL rendering, you may need to update your drivers.

Here is a video overview:

>[!VIDEO](https://video.tv.adobe.com/v/23559/?quality=12)

## Build a map visualization {#section_61BBFA3A7BFD48DA8D305A69D9416299}

1. From the list of visualizations, drag **[!UICONTROL Map]** into a Freeform panel:

   ![](assets/map-viz1.png)

1. Drag in a metric from the list of metrics (including calculated metrics).
1. Specify the data source you want to draw from. (This dialog appears only if you have location tracking enabled for mobile app data.) 

| Setting | Description |
| --- | --- |
| [!UICONTROL Mobile Lat/Long] | This option represents mobile app data. You see this option only if you have enabled it for your report suite in [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Report Suites] >  <select report suite> > [!UICONTROL Edit Settings] >  [!UICONTROL Mobile Management] > [!UICONTROL Enable Location Tracking]. This is the default setting (if location tracking is enabled). |
| [!UICONTROL Geographic Dimension] | This option represents geo segmentation data about visitor location based on the visitor's IP address. This data gets transformed into [!UICONTROL Country], [!UICONTROL Region], and [!UICONTROL City]. Note that it does not go to the DMA or Zip Code level. Almost all report suites have this dimension enabled. If yours does not, contact Adobe Customer Care to have geographic reports enabled. |

1. Click **[!UICONTROL Build]**.

   The first view you will see is a World View with a bubble map, similar to this.

   ![](assets/bubble-world-view.png)

1. You can now

    * **Zoom** into this map to magnify certain areas by double-clicking the map or by using your scroll wheel. The map zooms according to where you have placed your cursor. Through zoom interaction, the required dimension (country > state > city) is automatically updated, based on the zoom level.
    * **Compare** two or more map visualizations in the same project by placing them side by side.
    * **Show period-over-period (such as, year-over-year) comparisons**:

        * Show negative numbers: For example, if you are plotting a year-over-year metric, the map can show -33% over New York.
        * With metrics that are of type "percent", clustering averages the percentages together.
        * A green/red color scheme: Positive/Negative

    * **Rotate** the map in 2D or 3D by holding the [!UICONTROL Ctrl] key and moving the map.
    
    * **Toggle** to a different view, such as the heat map, using the [settings](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) described below. Note that the bubble view is the default setting.

1. **Save** the project to save all map settings (coordinates, zoom, rotation).
1. The freeform table, below the visualization, can be populated by dragging in location dimensions and metrics from the left rail:

   ![](assets/location-dimensions.png)

## Map visualization settings {#section_5F89C620A6AA42BC8E0955478B3A427E}

2 sets of settings exist for Map:

The **wrench icon** at the top right brings back the initial dialog where you can change the metric and the data source:

![](assets/map-wrench.png)

Clicking the **gear icon** reveals these visualization settings: 

| Setting | Description |
|--- |--- |
|Bubbles|Plots events using bubbles. A bubble chart is a multi-variable graph that is a cross between a scatterplot and a proportional area chart. This is the default view.|
|Heatmap|Plots events using a heatmap. A heatmap is a graphical representation of data where the individual values contained in a matrix are represented as colors.|
|Styles: Color Theme|Shows the color scheme for the heat map and bubbles. You can choose among Coral, Reds, Greens or Blues. Default is Coral.|
|Styles: Map Style|You can choose among Basic, Streets, Bright, Light, Dark, and Satellite.|
|Cluster Radius|Groups data points together that are within the specified number of pixels. Default is 50.|
|Custom Max Value|Lets you alter the threshold for the max value for the map - adjusting this value adjusts the scale for the bubbles/heatmap values (color and size) relative to the custom max value set.|

## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/26991/?quality=12)
