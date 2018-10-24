---
description: The resource monitor vector contains the Memory Budget Monitor and the Number of Queries Monitor.
seo-description: The resource monitor vector contains the Memory Budget Monitor and the Number of Queries Monitor.
seo-title: Query Queue Resource Monitors
solution: Analytics
title: Query Queue Resource Monitors
topic: Data workbench
uuid: f95d5bc5-2ed6-4f7e-86b1-893d05c557a8
index: y
internal: n
snippet: y
---

# Query Queue Resource Monitors

The resource monitor vector contains the Memory Budget Monitor and the Number of Queries Monitor.

 The following table describes the resource monitor fields used for query queuing.

<table id="table_9991EED2647A460FACA2DC80D4973A8E"> 
 <desc>
   Resource Monitors Parameters Table 
 </desc> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Memory Budget Monitor </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Monitors the query memory used by the current user group. If the current usage is between the Low Threshold and the High Threshold, no new bunches are scheduled until memory usage returns to below the Low Threshold value, for example, as a result of users closing their workspaces. Scheduled bunches are allowed to grow. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>High Threshold </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>The high threshold for memory usage (bytes). If the memory usage is above this value, no scheduling occurs, and the lowest priority-scheduled bunches are unscheduled one at a time, over a period of time, until the memory usage is brought to below this value. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Low Threshold </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>The low threshold for memory usage (bytes). If <span class="wintitle"> Memory Budget Monitor</span> value is below this value, new bunches are allowed to be scheduled, and scheduled bunches are allowed to grow. For example bunches grow when a user adds a visualization to a workspace. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Reaction Time </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>The time constant for the smoothing of the memory usage estimate. Smoothing values avoids reaction to usage spikes. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Number of Queries Monitor </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Monitors the total number of queries that are currently scheduled for the profile. This resource monitor lets you schedule bunches if the total number of queries remains below the value in the Low Threshold field. This monitor allows currently-scheduled bunches to grow if the total number of queries stays below the value in the High Threshold field. Additionally, this monitor removes bunches of a low priority in order to allow higher priority bunches to be scheduled or grow. However, this setting does not preempt bunches with a priority greater than specified in the Untouchable Priority field. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>High Threshold </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>The high threshold for memory usage (bytes). If the memory usage is above this value, no scheduling occurs, and the lowest priority scheduled bunches are unscheduled one at a time, over a period of time, until the memory usage is brought to below this value. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Low Threshold </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>The low threshold for memory usage (bytes). If <span class="wintitle"> Memory Budget Monitor</span> value is below this value, new bunches can be scheduled, and scheduled bunches can grow. </p> </td> 
  </tr> 
 </tbody> 
</table>

