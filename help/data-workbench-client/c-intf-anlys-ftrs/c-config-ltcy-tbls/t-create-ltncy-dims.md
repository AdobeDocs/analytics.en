---
description: Latency dimensions are constructed from a parent countable dimension, such as Sessions, and a time dimension, such as Day.
seo-description: Latency dimensions are constructed from a parent countable dimension, such as Sessions, and a time dimension, such as Day.
seo-title: Create a latency dimension
solution: Analytics
title: Create a latency dimension
topic: Data workbench
uuid: db3f84e6-84ed-427d-8003-5cc76fed6268
index: y
internal: n
snippet: y
---

# Create a latency dimension

Latency dimensions are constructed from a parent countable dimension, such as Sessions, and a time dimension, such as Day.

 When you create a latency table in Data Workbench, you automatically add a latency dimension to the visualization file ( [!DNL .vw]). You can edit a table’s latency dimension by following the steps below.

**To edit a latency dimension** 

1. Open the latency table that you created in a text editor such as Notepad. It is located in the User\*working profile name*\Work folder within your Data Workbench installation directory.

   The defined latency dimension includes the parameters shown in the following example. (The definition of your latency dimension may include additional parameters.) The [!DNL line entity = LatencyDim:] indicates the start of the latency dimension’s definition.

   ```
   entity = LatencyDim:
   Name = string: dimension name
   Level = ref: wdata/model/dim/level
   Clip = ref: wdata/model/dim/clip
   Time = ref: wdata/model/dim/time dimension
   Format = printf_format: 
   format = string: %+0.0f time string
   offset = double: offset
   Time Before = int: time before
   Time After = int: time after
   ```

1. Edit the values for the Name, Level, Clip, Time, Format, Time Before, or Time After parameters using the following table as a guide:

    <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> For this parameter... </th> 
   <th colname="col2" class="entry"> Provide this information... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Name </p> </td> 
   <td colname="col2"> <p>Optional. The name of the latency dimension that appears in the context menu when you right-click the dimension label or elements. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Level </p> </td> 
   <td colname="col2"> <p>A countable dimension that is the parent of the latency dimension. Examples include Session, Visitor, and Page View. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Clip </p> </td> 
   <td colname="col2"> <p>A countable dimension that has a one-to-many relationship with the level of the latency dimension. Latency is not calculated across the boundaries of this dimension. For example, if you specify a level of Page View and a clip of Session, latencies are calculated for those page views that occurred during the same session as the event. </p> <p>For information about one-to-many (simple) dimensions, see the <i>Dataset Configuration Guide</i>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Time </p> </td> 
   <td colname="col2"> <p>The dimension used to measure elapsed time for the latency dimension. This dimension can be a time dimension, such as Day or Hour, or a countable dimension, such as Visitor, Session, or Page View. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Format </td> 
   <td colname="col2"> <p>Optional. Specifies the appearance of the latency visualization in Data Workbench. Within the Format parameter, you can edit the following values: 
     <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
      <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">Time string. The unit of time shown in the latency visualization, such as day or week. Be sure to change the time string when you change the time dimension. </li> 
      <li id="li_E3B517ECE1494221AAE90455CC0AAB42">Offset. A whole number that is equal to the negative of the value for Time Before. For example, if Time Before is 7, the offset should be -7. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Time Before </p> </td> 
   <td colname="col2"> <p>The maximum amount of time (expressed in the units of the Time dimension) before the event for which latency is calculated. If this value is set to 0 or not set at all, latency is calculated only for the forward direction. </p> <p>If you change this value, be sure to change the offset value in the Format parameter: The offset is the negative of the value for Time Before. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Time After </p> </td> 
   <td colname="col2"> <p>The maximum amount of time (expressed in the units of the Time dimension) after the event for which latency is calculated. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Save the [!DNL .vw] file to the User\*working profile name*\Work folder.

   Following are the settings for the default latency dimension:

   ```
   entity = LatencyDim:
   Name = string: 
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Day
   Time Before = int: 7
   Time After = int: 7
   ```

   In the following latency dimension, the latency of each session event is calculated in hours and Time Before is set to zero. Therefore, latency is calculated for only those sessions that occurred within 24 hours after the defined event.

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```

