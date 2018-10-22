---
description: The primary tool used by system administrators is the Servers Manager.
seo-description: The primary tool used by system administrators is the Servers Manager.
seo-title: Servers Manager
solution: Analytics
title: Servers Manager
topic: Data workbench
uuid: c5058a51-d36b-4799-ad53-0939ff36a756
index: y
internal: n
snippet: y
---

# Servers Manager

The primary tool used by system administrators is the Servers Manager.

It is the main interface for determining overall system status and for performing system configuration, file management, and error monitoring functions.

The Servers Manager displays a colored dot (node) for each Data Workbench server and [!UICONTROL Sensor] installation in your system and provides at-a-glance system status for each installation. It also displays a node for your Data Workbench installation.

Green nodes represent active connections, red nodes represent connections that are disabled or otherwise inaccessible, and gray nodes represent connections whose states are undetermined.

![](assets/vis_SysStat_RedGreenDots.png)

Right-clicking a node displays information about the connecting component and provides access to any related menus.

The following tables describe the information provided when you right-click a node for Data Workbench, Data Workbench server (including a master Data Workbench server in a cluster), or [!UICONTROL Sensor].

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <desc> 
  <b>Data Workbench Servers Manager</b> 
 </desc> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Product name, version, and build number. </p> <p>Example: <span class="keyword"> Data workbench </span> 5.3 (00000001) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Address </p> </td> 
   <td colname="col2"> <p>IP address of the Data Workbench computer. </p> <p>Example: 100.0.0.1 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Configure </p> </td> 
   <td colname="col2"> <p>A link to your <span class="keyword"> Data Workbench’s </span> configuration file. Click <span class="uicontrol"> Configure </span> &gt; <span class="uicontrol"> Insight.cfg </span> to display the Data Workbench configuration window. Any changes that you make and save in this window are reflected in the <span class="filepath"> Insight.cfg </span> file in your Data Workbench installation directory. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Product name, version, and build number. </p> <p>Example: Data Workbench server 5.3 (00000001) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>The common name of the Data Workbench server computer. </p> <p>Example: <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Address </p> </td> 
   <td colname="col2"> <p>IP address or fully qualified domain name of the server as configured in the Addresses file on the computer and the Network Location parameter in the <span class="filepath"> Insight.cfg </span> file. </p> <p>Example: 100.0.0.1 </p> <p>For information about the Addresses file, see the <i>Server Products Installation and Administration Guide</i>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Current status of the Data Workbench server. This field displays OK when the Data Workbench server is running normally. If an error has occurred and the Data Workbench server node is red, the field displays the error (for example, “403 Forbidden”). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Detailed Status </p> </td> 
   <td colname="col2"> <p>A link to the <span class="keyword"> Data Workbench server </span> <span class="wintitle"> Detailed Status </span> interface, which is useful for troubleshooting errors or other issues with the Data Workbench server. </p> <p>For more information, see <a href="../c-admin-intrf/c-det-stat-interf.md#concept_99C2C8374C17448DB8A646F8D77BF72C" format="dita" scope="local"> The Detailed Status Interface </a>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Remote Desktop </p> </td> 
   <td colname="col2"> <p>Opens a <span class="wintitle"> Remote Desktop </span> session to the Data Workbench server computer. </p> <p>For more information, see <a href="../c-admin-intrf/t-rmt-dsktp-opt.md#task_DC0BDB4630474A17AF67B931BC22D9EF" format="dita" scope="local"> The Remote Desktop Option </a>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Server Files </p> </td> 
   <td colname="col2"> <p>A link to the <span class="wintitle"> Server Files Manager </span>, which displays the directories and files in the Data Workbench server installation directory. </p> <p>For more information, see <a href="../c-admin-intrf/c-svr-files-mgr.md#concept_73A0808487C8424285AE7302F53BC5F4" format="dita" scope="local"> The Server Files Manager </a>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Server Monitor </p> </td> 
   <td colname="col2"> <p>A link to the <span class="wintitle"> Server Monitor </span> interface, which is useful for troubleshooting or tracking performance parameters. </p> <p>For more information, see <a href="../c-admin-intrf/c-svr-mtr-intfc.md#concept_3BEA7441DE20409585E63060D5489F45" format="dita" scope="local"> The Server Monitor Interface </a>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Related Servers </p> </td> 
   <td colname="col2"> <p>For Data Workbench server clusters only. </p> <p>A menu that lists the common names of the computers listed in the master <span class="filepath"> Data Workbench server’s *.address </span> file. This list usually includes all of the processing <span class="keyword"> Data Workbench servers </span> in the cluster. This menu appears only if Data Workbench has a copy of the master <span class="filepath"> Data Workbench server’s *.address </span> file. </p> <p>When you click <span class="uicontrol"> Related Servers </span>, you can click either: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Server Monitor List </span>, which displays the <span class="wintitle"> Server Monitor </span> interface listing details for all of the related servers </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">The common name of any Data Workbench server, which displays a context menu that enables you to open any of the following for that particular server: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Detailed Status </span>. See <a href="../c-admin-intrf/c-det-stat-interf.md#concept_99C2C8374C17448DB8A646F8D77BF72C" format="dita" scope="local"> The Detailed Status Interface </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Remote Desktop </span>. See <a href="../c-admin-intrf/t-rmt-dsktp-opt.md#task_DC0BDB4630474A17AF67B931BC22D9EF" format="dita" scope="local"> The Remote Desktop Option </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Server Files Manager </span>. See <a href="../c-admin-intrf/c-svr-files-mgr.md#concept_73A0808487C8424285AE7302F53BC5F4" format="dita" scope="local"> The Server Files Manager </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Server Monitor </span>. See <a href="../c-admin-intrf/c-svr-mtr-intfc.md#concept_3BEA7441DE20409585E63060D5489F45" format="dita" scope="local"> The Server Monitor Interface </a>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_5BFA0AFE2D9A4337BF04343879DAD03B"> 
 <desc> 
  <b> Sensor Servers Manager </b> 
 </desc> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Product name, version, and build number. </p> <p>Example: Sensor 3.76; J3.67 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> The <span class="wintitle"> Sensor </span> ID specified in the <span class="wintitle"> Sensor </span> configuration file for this installation. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>IP address of the web or application server on which <span class="wintitle"> Sensor </span> is installed. </p> <p>Example: 100.0.0.1 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>Process ID assigned by the operating system. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Whether <span class="wintitle"> Sensor </span> and the Data Workbench server communicate using SSL. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Time </p> </td> 
   <td colname="col2"> <p>Time (HH:MM:SS) that the <span class="wintitle"> Sensor </span> last established a connection with the Data Workbench server. </p> </td> 
  </tr> 
 </tbody> 
</table>

