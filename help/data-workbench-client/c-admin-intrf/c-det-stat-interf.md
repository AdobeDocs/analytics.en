---
description: The Detailed Status interface is useful for troubleshooting errors or other issues with Data Workbench server computers.
seo-description: The Detailed Status interface is useful for troubleshooting errors or other issues with Data Workbench server computers.
seo-title: Detailed Status interface
solution: Analytics
title: Detailed Status interface
topic: Data workbench
uuid: f61f4398-0d55-4e35-b2f6-802f6b9cf5d3
index: y
internal: n
snippet: y
---

# Detailed Status interface

The Detailed Status interface is useful for troubleshooting errors or other issues with Data Workbench server computers.

This includes any [!UICONTROL Transform] profiles running on those computers, or [!DNL Report] computers that are clients of the Data Workbench server. You can access [!UICONTROL Master Server] and [!UICONTROL Query Server Detailed Status] interfaces through the [!UICONTROL Admin] menu. To access the [!UICONTROL Detailed Status] interface for other computers, in the [!UICONTROL Servers Manager], right-click the node of the server for which you want to view status and click **[!UICONTROL Detailed Status]**. See [The Servers Manager](../../data-workbench-client/c-admin-intrf/c-svrs-mgr.md#concept_2DFFF1CA5BCE470A8EE854ED57CBE5BA).

For more information about the Data Workbench server, see the *Server Products Installation and Administration Guide*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>To update the information in a [!UICONTROL Detailed Status] interface, right-click the **[!UICONTROL Detailed Status]** heading and click **[!UICONTROL Refresh]**.

The following table lists the tasks that can be completed using the [!UICONTROL Detailed Status] interface.

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <desc> 
  <b> <span class="wintitle"> Detailed Status</span> interface tasks </b> 
 </desc> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> To perform this task... </th> 
   <th colname="col2" class="entry"> Do this... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>To display each computer component and its current status </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Component Status</span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To display how much memory on the computer is being used </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Memory Status</span> &gt; <span class="uicontrol"> Address Space Load</span>. </p> <p>For more information about monitoring address space load, see the <i>Server Products Installation and Administration Guide</i>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To determine whether the computer is configured to use the /3GB Switch </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Memory Status</span> &gt; <span class="uicontrol"> Process Address Space</span>. </p> <p>If the <span class="wintitle"> Total</span> field displays more that 3000000 KB, your computer is configured to use the /3GB Switch. </p> <p>For more information about the /3GB Switch, see the <i>Server Products Installation and Administration Guide</i>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To monitor the amount of disk space and memory used to store each dimension as well as that used to store the names of its elements </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Performance</span> &gt; <span class="uicontrol"> Dimensions</span> &gt; <span class="uicontrol"> Disk Usage</span> &gt; <i>&lt;<span class="uicontrol"> profile name</span>&gt; </i>or <span class="uicontrol"> Performance</span> &gt; <span class="uicontrol"> Dimensions</span> &gt; <span class="uicontrol"> Memory Usage</span> &gt; <i>&lt;<span class="uicontrol"> profile name</span>&gt;</i>. </p> <p>The <span class="wintitle"> Disk Usage</span> fields provide the name and amount of disk space (in MB) required to store each dimension. Large disk usage numbers can adversely affect query times because the Data Workbench server has to read through all the data to complete related queries. Lowering the disk usage for a dimension can reduce the time it takes to complete related queries. </p> <p>The <span class="wintitle"> Memory Usage</span> fields provide the number of elements in each dimension and the amount of memory required to store the list of element names. Large numbers of elements can adversely affect the amount of memory being used during a query because the Data Workbench server has to read through each element. Reducing the number of elements in a dimension can reduce the time it takes to complete related queries. </p> <p>Example: 
     <codeblock>
      +&nbsp;Performance
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Dimensions&nbsp;
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Disk&nbsp;Usage
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;1.386&nbsp;MB
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Memory&nbsp;Usage
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;21&nbsp;elements,&nbsp;0.001&nbsp;MB
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
     </codeblock> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To monitor the CPU usage for the stages within Log Processing and Transformation </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Performance</span> &gt; <span class="uicontrol"> CPU Usage</span> &gt; <span class="uicontrol"> Log Processing</span> &gt; <i>&lt;<span class="uicontrol"> profile name</span>&gt;</i> or <span class="uicontrol"> Performance</span> &gt; <span class="uicontrol"> CPU Usage</span> &gt; <span class="uicontrol"> Transformation</span> &gt; &lt;<span class="uicontrol"> profile name</span>&gt;. </p> <p>Each of these sets of fields provides you with the CPU Usage (in seconds) for each of the stages within Log Processing and Transformation. </p> <p>Example: 
     <codeblock>
      +&nbsp;Performance
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec
     </codeblock> </p> <p>The time that it takes to complete a query is usually proportional to the total size of all of your dimensions. After reviewing the size of each dimension, you can evaluate whether a particular dimension is useful enough and used often enough to justify the performance cost of the dimension. If it is not, you can delete the dimension in the <span class="wintitle"> Profile Manager</span>. See<a href="../../data-workbench-client/c-admin-intrf/c-prof-mgr/c-prof-mgr.md#concept_2C8F60CC84D044BFB57DDF947B1DB263" format="dita" scope="local"> The Profile Manager</a>. </p> <p>A dimension whose list of element names is excessively large (that is, more than 128 MB) may cause “Out of memory” errors even if the total address space usage is not near the limit. </p> <p>Also, if you are using a Data Workbench server cluster but not using centralized normalization, a dimension whose list of element names is large has a significant impact on send memory budgets. For more information about centralized normalization, see the <i>Dataset Configuration Guide</i>. If the amount of memory required to store all of the lists of element names combined is more than 100 MB across all of the servers in the cluster, you might receive “Send memory budget exceeded” errors even when query activity is light. For example, if you have a four-server cluster with more than 25 MB on each server being used to store the lists of element names, you might receive errors. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To monitor the time spent in Log Processing and Transformation </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Performance</span> &gt; <span class="uicontrol"> CPU Usage</span> &gt; <span class="uicontrol"> Log Processing</span> &gt; <i>&lt;<span class="uicontrol"> profile name</span>&gt;</i> or <span class="uicontrol"> Performance</span> &gt; <span class="uicontrol"> CPU Usage</span> &gt; <span class="uicontrol"> Transformation</span> &gt; <i>&lt;<span class="uicontrol"> profile name</span>&gt;</i>. </p> <p>Reviewing the fields in these sections enables you to identify filters and transformations that may be negatively affecting the amount of time needed for Log Processing and Transformation. You then can make design decisions regarding individual filters and transformations with long processing times. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To monitor disk space usage and increase query speed </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Performance</span> &gt; <span class="uicontrol"> Log Processing Fields</span> &gt; <i>&lt;<span class="uicontrol"> profile name</span>&gt;</i>. </p> <p>Each line item in this section corresponds to a parameter in the <span class="filepath"> Log Processing.cfg</span> file. Reviewing these fields enables you to see how much memory each parameter is using. You then can make design decisions regarding individual items that are quite large. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To determine the elapsed time of previous reprocessing or transformation </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Processing Status</span> &gt; <i>&lt;<span class="uicontrol"> profile name</span>&gt;</i> &gt; <span class="uicontrol"> Processing Mode History</span>. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Real Time - time that the Data Workbench server was available for making queries. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Fast Input - this time plus the Fast Merge time is the is the total time needed for processing the dataset. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Fast Merge - total time needed for transforming the dataset. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To diagnose “As-of time” issues </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Processing Status</span> &gt; <i>&lt;<span class="uicontrol"> profile name</span>&gt;</i> &gt; <span class="uicontrol"> As Of Time</span> &gt; <span class="uicontrol"> Sources as-of</span>. </p> <p>Reviewing the as-of times for each source can help you determine which source(s) may be negatively affecting the Overall As-of. You then can address the problems with those particular sources. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To estimate how long a running query takes to complete </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Execution Engine</span>. </p> <p>Reviewing the <span class="wintitle"> Data Sweep Time</span> field provides you with an estimate of how long it takes for a query to complete. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To list all profiles available on this computer and details about their status </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Profiles</span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To view Replication status </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Component Status</span>. </p> <p>Check the status of the Replicate component. If Replication is running, OK displays. If the Replicate component has failed, an error message displays. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To view <span class="wintitle"> Report Server</span> status for a <span class="keyword"> Report</span> computer that connects to the Data Workbench server </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Report Server Status</span>. </p> <p>This section of the <span class="wintitle"> Detailed Status</span> interface includes a copy of the <span class="filepath"> Report Server.cfg</span> file, information about the number of reports that are running (Current Slice), and information about the most recent error (Last Error). </p> <p>For steps to edit the <span class="filepath"> Report Server.cfg</span> file, see the <i><span class="keyword"> Data Workbench</span> Report Guide</i>. </p> <p> <p>Note: If the <span class="wintitle"> Report Server Status</span> section does not appear in the <span class="wintitle"> Detailed Status</span> interface, you may need to configure the Data Workbench server to display <span class="wintitle"> Report Server Status</span>. For steps, see the <i><span class="keyword"> Data Workbench</span> Report Guide</i>. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To view memory usage information for Transform </p> </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Processing Status</span> &gt; <span class="uicontrol"> Transform</span>. </p> <p>For more information about Transform, see the <i>Server Products Installation and Administration Guide</i> and the <i>Dataset Configuration Guide</i>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To save the <span class="wintitle"> Detailed Status</span> interface as a <span class="filepath"> *.cfg</span> file that can be opened in a text editor such as Notepad or distributed to others </p> </td> 
   <td colname="col2"> <p>Right-click the <span class="uicontrol"> Detailed Status</span> heading and click <span class="uicontrol"> Save Copy As</span>. </p> <p>Note:  <p>Right-clicking the <span class="uicontrol"> Detailed Status</span> heading and clicking <span class="uicontrol"> Save</span> to <i>server name</i>/Status/ does not work in the <span class="wintitle"> Detailed Status</span> interface. The following error message appears: </p> <p>Unable to save /Status/. 403 Forbidden </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>To view <span class="uicontrol"> Rows per Log Source</span> metric </p> </td> 
   <td colname="col2"> <p>If Rows per Log Source metric needs to be reported in Detailed Status, then the Data Workbench Administrator should define the "Log Source ID" and provide a unique name in Custom Profile's Log Processing.cfg. </p> </td> 
  </tr> 
 </tbody> 
</table>

