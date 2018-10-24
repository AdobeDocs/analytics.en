---
description: The Server Monitor interface is useful for troubleshooting or simply tracking the performance parameters of Data Workbench server computers and Report computers that are clients of Data Workbench server computers.
seo-description: The Server Monitor interface is useful for troubleshooting or simply tracking the performance parameters of Data Workbench server computers and Report computers that are clients of Data Workbench server computers.
seo-title: Server Monitor interface
solution: Analytics
title: Server Monitor interface
topic: Data workbench
uuid: f16dac87-747c-45d1-94e9-2043ea244b14
index: y
internal: n
snippet: y
---

# Server Monitor interface

The Server Monitor interface is useful for troubleshooting or simply tracking the performance parameters of Data Workbench server computers and Report computers that are clients of Data Workbench server computers.

The Server Monitor interface displays either a green dot or a red dot at its top, to the left of the computer name. A green dot indicates that the computer is functioning without issue. A red dot indicates that one or more errors have occurred on the computer.

The lower portion of the Server Monitor interface lists the processing status of each of your available profiles as well as performance details about the computer.

For more information about [!DNL Data Workbench servers], see the *Server Products Installation and Administration Guide*. For more information about [!DNL Report], see the * [!DNL Data Workbench] Report Guide*.

**To open the Server Monitor interface**

* In the Servers Manager, right-click the node of the Data Workbench server or [!DNL Report] computer. t

Click **[!UICONTROL Server Monitor]** to view details about one server, or click **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** to view details about a cluster of related servers.

![](assets/vis_ServerMonitor.png)

The [!UICONTROL Server Monitor]interface updates automatically every 10 seconds.

The following table lists the tasks that can be completed using the [!UICONTROL Server Monitor] interface.

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> To perform this task... </th> 
   <th colname="col2" class="entry"> Do this... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>To check the log processing status of a profile </p> </td> 
   <td colname="col2"> <p>View the Profile <i>Profile</i> Name vector. In the example above, you would view the Profile ExampleProfile vector to see that the ExampleProfile profile processes on one server and its log processing is 100% complete. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To determine how long the computer takes to respond to requests </p> </td> 
   <td colname="col2"> <p>View the poll latency field. If this value is greater than 1000ms, contact Adobe Support Services. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To view an estimate of how long it might take to complete transformation or querying </p> </td> 
   <td colname="col2"> <p>View the sweep time (hh:mm:ss) field, which is present only during transformation or querying. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To determine the current number of network connections to the computer </p> </td> 
   <td colname="col2"> <p>View the last line of the computer’s <span class="wintitle"> Server Monitor</span> information. In the example above, you see that 2 network connections are currently coming from one computer. </p> </td> 
  </tr> 
 </tbody> 
</table>

