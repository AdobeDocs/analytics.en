---
description: Process maps can be configured to work with any combination of base dimension, group dimension, level dimension, and metric that makes sense for your application and dataset.
seo-description: Process maps can be configured to work with any combination of base dimension, group dimension, level dimension, and metric that makes sense for your application and dataset.
seo-title: Configure a process map
solution: Analytics
title: Configure a process map
topic: Data workbench
uuid: 9353916a-d64b-4e22-a86b-d4faca31b0a6
index: y
internal: n
snippet: y
---

# Configure a process map

Process maps can be configured to work with any combination of base dimension, group dimension, level dimension, and metric that makes sense for your application and dataset.

 After you configure a process map, it is listed with other process maps in the [!UICONTROL Add Visualization menu]. 

1. In the [!UICONTROL Profile Manager], click **[!UICONTROL Menu]**, click **[!UICONTROL Add Visualization]**, then click the type of process map type that you want to configure (2D Metric Map, 2D Process Map, or 3D Process Map).

   At least one [!DNL *.vw] file resides in the directory. 

1. Right-click the check mark for the desired file and click **[!UICONTROL Make Local]**.
1. Right-click the check mark for the file in the [!UICONTROL User] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Edit the parameters of the file using the following sample file and table as guides:

   ```
   window = simpleBorderWindow: 
     client = processMap: 
       Traffic Metric = ref: wdata/model/metric/metric name
       center = v3d: (-0.741014, 0, 0.0639476)
       color_links = bool: true
       Map = PrefixDim: 
         Name = string: Map
         Base Dimension = ref: wdata/model/dim/base dimension name
         Element Prefixes = vector: 0 items
         Element Names = vector: 0 items
       Map Level = ref: wdata/model/dim/level dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       node_label = vector<bool>: 
       node_positions = vector: 0 items
       quantify_links = int: 2
       range = double: 2.37386
       size = v3d: (430, 290, 0)
       xAxisMetric = ref: wdata/model/metric/metric name for metric map
     pos = v3d: (880, 595, 0)
     size = v3d: (430, 309, 0)
   ```

<table id="table_3F072DB1B68746C49DF9332718982EBE"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> For this parameter... </th> 
   <th colname="col2" class="entry"> Provide this information... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p><i>Metric name</i> </p> </td> 
   <td colname="col2"> <p>The name of the metric whose value for a given node is proportional to the size of the node. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p><i>Base dimension name</i> </p> </td> 
   <td colname="col2"> <p>The name of the dimension whose elements appear as nodes on the process map. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p><i>Level dimension name</i> </p> </td> 
   <td colname="col2"> <p>The name of the level (parent) of the base dimension whose elements you drag to the process map. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p><i>Group dimension name</i> </p> </td> 
   <td colname="col2"> <p>The name of the dimension that determines how the elements of the level dimension are grouped to form the connections between nodes. A connection between two nodes cannot span more than one element of a group dimension. When you make a selection based on a node within a process map, you are selecting all of the elements of the group dimension that involved that node. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p><i>Metric name for metric map</i> </p> </td> 
   <td colname="col2"> <p>This parameter applies to 2D metric maps only. </p> <p>The name of the metric whose value determines the horizontal position of the nodes on the map. </p> </td> 
  </tr> 
 </tbody> 
</table>

   >[!NOTE]
   >
   >For more information about the base dimension, group dimension, level dimension, and metric for a process map, see [Process Maps](../c_analysis_vis/c_proc_maps/c_proc_maps.md#concept_880AEE224404429785B733A4E80D275E).

1. In Notepad, click **[!UICONTROL File]** > **[!UICONTROL Save As]** to save the file with a new name based on the base dimension, that is, *Base dimension name*.vw.

   (If you are configuring a 2D metric map, you should save the file with a name based on the metric name for the metric map, that is, *Metric name for metric map*.vw.) Make sure that you save the file to the appropriate process map directory.

   >[!NOTE]
   >
   >To make sure that your process map is saved as a [!DNL *.vw] file, in the [!UICONTROL Save As] window, set Save as type to All Files.

1. (Optional) To make the changes available to all users of the working profile, in the [!UICONTROL Profile Manager], right-click the check mark for the file in the [!UICONTROL User] column and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*.
