---
description: The Worktop is where you organize and access all of your workspaces and reports.
seo-description: The Worktop is where you organize and access all of your workspaces and reports.
seo-title: Worktops
solution: Analytics
title: Worktops
topic: Data workbench
uuid: c1448c38-5441-4fe2-a9bc-993dca2a3860
index: y
internal: n
snippet: y
---

# Worktops

The Worktop is where you organize and access all of your workspaces and reports.

In most cases, the [!UICONTROL Worktop] is displayed immediately after you open Data Workbench. The features of the [!UICONTROL Worktop] include the sidebar and tabbed interface. Additionally, the sidebar lets you add visualizations and access regularly-used functions.

**Worktop**

![](assets/client-wktp.png)

The [!UICONTROL Worktop] also enables you to create and save new and updated workspaces and reports, as well as publish workspaces and reports to the Data Workbench server for others to access.

The [!UICONTROL Worktop] elements table below describes each element of the [!UICONTROL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689"> 
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Sidebar </td> 
   <td colname="col2"> <p>The sidebar provides context and control for workspaces, as well as awareness of the current state of a workspace and access to regularly-used functions. The following functions are available in the sidebar: </p> <p> <b>Connection:</b> A status indicator showing the online status. Click the connection status to enable or disable <span class="wintitle"> Work Online</span>. See <a href="../../data-workbench-client/c-get-started/c-off-on.md#concept_CEF8758EDE044B18B3558376C5EB9F54" format="dita" scope="local"> Working Offline and Online</a>. </p> <p> <b>Profile:</b> An indicator of the current profile in use. </p> <p> <b>As Of: </b>A status indicator showing how up-to-date the data is in the profile’s data set. This data is downloaded and processed from the DPU server, which can occur only when you are working online. </p> <p> <b>Query/Sample Confidence:</b> An indicator of the query completion. When the status queries to 100 percent, all of the data has been queried. </p> <p> <b>Add:</b> Lets you add visualizations like panels, legends, and tables to the sidebar. See <a href="../../data-workbench-client/c-get-started/c-config-sidebar.md#section_666F70A405DB4F8D8EAFFA567FFCAC06" format="dita" scope="local"> Adding Visualizations to the Sidebar</a>. </p> <p> <b>Options:</b> Lets you revert to a previous sidebar setting, and to automatically hide the sidebar. </p> <p>Sidebar settings are saved in the <span class="filepath"> sidebar.vw</span> file when you close Data Workbench. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Tab and Subtab or Drop-down subdirectories (not shown) </p> </td> 
   <td colname="col2"> <p>Each tab that appears on the <span class="wintitle"> Worktop</span> corresponds to the tab’s <i>working profile name</i>\Workspaces\<i>tab name</i> folder within the Data Workbench installation directory and represents a particular type of information, such as Dashboards, Activity, Acquisition, Visitors, and so on. The subfolders in the tab name folder display as subtabs by default, but they also can be displayed as subdirectories. See <a href="../../data-workbench-client/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept_0F1E6061B03949199326DC6DF71A52BC" format="dita" scope="local"> Customizing Worktop Tabs</a>. </p> <p> <p>Note:  Each Data Workbench profile is delivered with a standard set of tabs. Because your implementation can be fully customized, the workspaces (and, therefore, tabs) that appear may differ from what is documented in this guide. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Profile Status </td> 
   <td colname="col2"> Provides the connection status to the Data Workbench server and the name of the currently loaded profile. The As Of date and time for the data in the profile’s dataset display below the online indicator. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Minimize, Maximize, Close </td> 
   <td colname="col2"> Standard Windows functions. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Thumbnails </td> 
   <td colname="col2"> <p>A thumbnail is a snapshot of a workspace that appears on the <span class="wintitle"> Worktop</span>. A new snapshot is taken every time you save the workspace. Thumbnails enable you to quickly identify a particular workspace on the <span class="wintitle"> Worktop</span>. </p> <p>To open a workspace, click the thumbnail. </p> <p> <p>Note:  Each Data Workbench profile is delivered with a standard set of workspaces. Because your implementation can be fully customized, the workspaces (and, therefore, thumbnails) that appear may differ from what is documented in this guide. </p> </p> <p>For more information about workspaces, see <a href="../../data-workbench-client/c-get-started/c-config-sidebar.md#concept_41DB771B302E43018E5A9DAA40B397E6" format="dita" scope="local"> Configuring the Sidebar</a>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Error messages </td> 
   <td colname="col2"> <p>Error messages display in red below the status. For status code descriptions, see <a href="https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>. </p> <p>For example: 403_Forbidden. </p> </td> 
  </tr> 
 </tbody> 
</table>

