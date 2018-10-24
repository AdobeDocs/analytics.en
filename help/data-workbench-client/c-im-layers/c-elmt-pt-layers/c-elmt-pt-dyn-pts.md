---
description: When creating an element point layer using dynamic points, the latitude and longitude data is embedded in each element of the dimension.
seo-description: When creating an element point layer using dynamic points, the latitude and longitude data is embedded in each element of the dimension.
seo-title: Define element point layers using dynamic points
solution: Analytics
title: Define element point layers using dynamic points
topic: Data workbench
uuid: fd819131-97ca-42c2-8dea-74348370861b
index: y
internal: n
snippet: y
---

# Define element point layers using dynamic points

When creating an element point layer using dynamic points, the latitude and longitude data is embedded in each element of the dimension.

To define an element point layer using dynamic points, you must create or already have available the following:

* A dimension, defined in the [!DNL Transformation.cfg] file or a [!UICONTROL transformation dataset include] file, in which each element contains the string “latitude,longitude” or “latitude,longitude,name.”

  For steps to create a dimension, see the *Dataset Configuration Guide*. 

* A layer file that specifies the related dimension.

For more information about the required format of the layer file, see [Element Point Layer File Format](../../../data-workbench-client/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#section_0645FBC761C14BB986F3D6F02DF407A0).

>[!NOTE]
>
>When using [!UICONTROL Dynamic Points], it is essential to ensure that the cardinality of the dimension specified in the layer file is reasonable. If every row of a dataset has a different latitude and longitude, the dimension quickly fills up and most rows fall into a Small Elements element. Because the Small Elements element does not have a latitude and longitude, it does not appear on the globe.

## Element point layer file format {#section_0645FBC761C14BB986F3D6F02DF407A0}

Each element point layer file using dynamic points must be formatted using the following template: 

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_8756BDCC49F447C0855BA64BC0078A0C"> 
 <desc> 
  <b>Element point layer parameters: dynamic points </b> 
 </desc> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2"> <p>The name of the dimension (defined in a transformation configuration file), which must contain elements with the string “latitude,longitude” or “latitude,longitude,name” as shown in the following examples: 
     <ul id="ul_CC12F05459C640F5AB3C295932B04F83"> 
      <li id="li_9023CFA04A0F407E9DF0E1A4D71BB18C">37.5181,-77.1903 </li> 
      <li id="li_F002AB3AB98049A4AF1588B51167C7FA">35.3317,-77.8126,Somewhere </li> 
     </ul> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Metric </td> 
   <td colname="col2"> The name of the metric that is evaluated over the dimension specified in the Dimension parameter. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Dynamic Points </td> 
   <td colname="col2"> Enables Dynamic Points. Set to true. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Scale </td> 
   <td colname="col2"> Optional. Value used to size the points in the layer. The default value is 100. Larger values make the points bigger, and smaller values make them smaller. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Color </td> 
   <td colname="col2"> Optional. The RGB color vector, which is expressed as (red,green,blue). For each color in the vector, you can enter a value from 0.0 to 1.0. For example, (1.0, 0.0, 0.0) is bright red, and (0.5, 0.5, 0.5) is gray. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Rendering Mode </td> 
   <td colname="col2"> <p>Optional. Integer value representing the rendering mode to use for the layer. The three available modes are as follows: 
     <ul id="ul_C7A74B9B085741C8B7116E4F110DF830"> 
      <li id="li_75CC2BE35C594B6895F743A1967A2E07">Rendering Mode 1. Points size is defined in screen space (points stay a constant size relative to the computer screen). Points are rendered using polygons, so there is no upper limit on point size. This is the default rendering mode. </li> 
      <li id="li_5B19C5B0F59548E28DCE7F7CD319E210">Rendering Mode 2. Point size is defined in world space (points stay a constant size relative to the globe). Points are rendered using polygons, so there is no upper limit on point size. </li> 
      <li id="li_DF0C9AEFE82642C9BD5AEA79770D2896">Rendering Mode 3. Point size is defined in screen space. Points are rendered using OpenGL smooth points. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

The [!DNL IP Coordinates.layer] file is formatted as follows: 

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```

