---
description: A 3D Scatter Plot graphs the elements of a data dimension (such as Days or Referral Site) on a three-dimensional grid where the x, y, and z axes represent various metrics.
seo-description: A 3D Scatter Plot graphs the elements of a data dimension (such as Days or Referral Site) on a three-dimensional grid where the x, y, and z axes represent various metrics.
seo-title: 3D scatter plots
solution: Analytics
title: 3D scatter plots
topic: Data workbench
uuid: 8b2992e3-5d22-4bbe-8625-f22e61c8e06d
index: y
internal: n
snippet: y
---

# 3D scatter plots

A 3D Scatter Plot graphs the elements of a data dimension (such as Days or Referral Site) on a three-dimensional grid where the x, y, and z axes represent various metrics.

Like [Scatter Plot 2D](https://marketing.adobe.com/resources/help/en_US/insight/client/index.html#Scatter_Plots), this visualization is useful when trying to understand the relationship between large numbers of disparate items employing different metrics.

**To employ the 3D scatter plot visualization:**

1. Open a new workspace.

   After opening a new workspace, you may need to click **Add** > **Temporarily Unlock**. 

1. Right-click and select **Visualization** > **3D Scatter Plot**.

   A menu listing **[!UICONTROL Dimensions]** will open. 

1. Select a dimension for the query.

   The 3D Scatter Plot will open the default metrics for that dimension.

   ![](assets/3D_main.png)

   Selecting the **[!UICONTROL Days]** menu displays the following 3D Scatter Plot with these default metrics on the following axes: **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]**, and **[!UICONTROL z=Visits]**. 

1. Change metrics. Right-click on the metric label in the x, y, or z axis and select **[!UICONTROL Change Metric]**. Then select a different metric for the selected axis.

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * Drag a metric to one of the three axis labels and drop it to change the selected axis to the dropped metric. 
   >    * Drag a metric anywhere else on the visualization and drop it to change the radius metric for that axis. 
   >    * Drag a dimension to anywhere on the visualization and drop it to change the dimension for the visualization. 
   >    
   >

1. Change the Radius Metric. Right-click the title at the top of the page (titled after the selected dimension) and select **[!UICONTROL Change Radius Metric]**.

   The radius metric defines the size of the plotted point based on the metric selection. The relative position of points does not change in the scatter plot, but the plotted point sizes within the visualization increase based on the metric value.

   ![](assets/3D_change_radius.png)

1. Employ the **[!UICONTROL Orthographic Camera]**. This option lets you identify the plotted points in relation to their true perspective based on the radius metric to avoid three-dimensional distortion.

   When the 3D Scatter Plot first appears, it displays in a three-dimensional rotating projection, which causes some distortion for points plotted nearer to the perspective, or virtual "camera." (The plots nearer to the camera show up much larger than the points rotating further away from the camera.)

   To avoid this perspective distortion, you can select the **[!UICONTROL Orthographic Camera]** option by right-clicking on the title and selecting from the menu. This allows you to represent the three-dimensional objects in two-dimensions. This renders the plotted points as flat and displays the points as relative to the radius metric, lessening the 3-dimensional offsets.

1. Select points from the scatter plot.

    * **To remove a point or group of points**: Click the point. 
    * **To add another point or group of points to your selection**: **Ctrl** + **click** a point or **Ctrl** + **drag** across multiple points. 
    
    * **To remove a point or group of points from your selection**: **Shift** + **click** a point or **Shift** **+** **drag** across several points.

