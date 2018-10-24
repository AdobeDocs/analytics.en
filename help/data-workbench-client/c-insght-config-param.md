---
description: Set the parameters in the Insight.cfg file to specify your network connection and Data Workbench configuration settings.
seo-description: Set the parameters in the Insight.cfg file to specify your network connection and Data Workbench configuration settings.
seo-title: Configuration parameters
solution: Analytics
title: Configuration parameters
topic: Data workbench
uuid: 3568caa7-270a-4e9d-9a48-6c530e98669f
index: y
internal: n
snippet: y
---

# Configuration parameters

Set the parameters in the Insight.cfg file to specify your network connection and Data Workbench configuration settings.

 The following example contains only the parameters included in the [!DNL Insight.cfg] file by default.

**New Layout view**

![](assets/config_tree_new_layout.png)

**Original Layout view**

![](assets/cfg_Workstation_AddServer.png)

Some of the parameters available in the new [!DNL Insight.cfg] file may not available in your version of the [!DNL Insight.cfg] file. If one of these parameters is needed, you must add it to the [!DNL Insight.cfg] file using [!UICONTROL Add Custom Key], by right-clicking on a parameter, then specifying the name and type. You can also add parameters by opening the [!DNL .cfg] file (located in the Data Workbench installation directory) using a text editor.

Following is an example of all of the parameters available for the [!DNL Insight.cfg] file that you can use as a model for adding parameter entries: 

```
Licensing = serverInfo:
  Proxy Address = string: 
  Proxy Port = int: 8080
  Proxy User Name = string: 
  Proxy Password = string: 
Servers = vector: 1 items
  0 = serverInfo: 
    Address = string: VS02
    Name = string: Insight Server
    Port = int: 443
    Proxy Address = string: 
    Proxy Password = string: 
    Proxy Port = int: 8080
    Proxy User Name = string: 
    SSL Client Certificate = string: Named User.pem
    SSL Server Common Name = string: VS02
    Use Address File = bool: false
    Use SSL = bool: true
Color Set = int: 0
Default to Online = bool: false
Fonts = vector: 0 items
Gamma = float: 1.6
Maximum Sample Size (MB) = double: 0
Network Location = string: 
Unhide All = bool: false
Unlock = bool: false
Update Software = bool: true
User Folder = string: User\\
Toolbar Icons = bool: false
```

The following table provides descriptions of the available [!DNL Insight.cfg] file parameters in alphabetical order.

<table id="table_4465713A08B649E280A3B4840E829518"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Address </p> </td> 
   <td colname="col2"> <p>The host name or numeric IP address of your Data Workbench server computer. </p> <p>Example: <span class="filepath"> vsServer.mycompany.com or 192.168.1.90</span> </p> <p>If <span class="wintitle"> Address</span> is not specified, <span class="keyword"> the client</span> uses the common name specified in the SSL Server Common Name parameter when Use Address File is set to false. </p> <p> <p>Note: If the Use Address File parameter is set to true, the text entered in the Address parameter can be removed after the first profile is opened on <span class="keyword"> the client</span>. Then the setting for Network Location Parameter determines which addresses from the Address file for the cluster are used for connecting to the master server. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Color Set </p> </td> 
   <td colname="col2"> <p>Specifies the background color of your <span class="keyword"> client application</span>. The options are as follows: </p> <p>0 = black </p> <p>1 = white </p> <p>2 = monochrome </p> <p>The default value is 0, black. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Default Online Level </p> </td> 
   <td colname="col2"> <p>Optional. Enables you to make your instance of Data Workbench work by default as streaming, offline or online each time it opens. The options are Streaming, Online, or Offline. The default configuration for Data Workbench is to work Offline. </p> <p> <p>Note: Before deciding to work online by default, make sure to weigh the benefits and consequences outlined in <a href="../../data-workbench-client/c-get-started/c-off-on.md#concept_CEF8758EDE044B18B3558376C5EB9F54" format="dita" scope="local"> Working Offline and Online</a>. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Fonts </p> </td> 
   <td colname="col2"> <p>Optional. Vector listing the fonts that <span class="keyword"> the client</span> should use to render UTF8-based unicode special characters. The number of fonts in the list is unlimited. </p> <p>The first font should always be Lucida Sans Console. If this parameter is not included in the <span class="filepath"> Insight.cfg</span> file, Data Workbench uses only Lucida Sans console to display text. </p> <p> <span class="keyword"> Data workbench</span> uses the first font in the list to render all characters until it encounters a character that it cannot render. It uses the second font in the list to render that character. If that font does not render the character, Data Workbench uses the third font in the list to render that character, and so on, until it reaches the end of the font list. If the correct font is not listed in the vector, Data Workbench displays the hexadecimal value for the character. </p> <p> <p>Note:  Do not change this parameter while Data Workbench is running. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Gamma setting for the Data Workbench display. The default value is 1.6. Adobe does not recommend changing this value. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Licensing </p> </td> 
   <td colname="col2"> <p>Optional. You need to modify the parameters in the Licensing vector only if you are contacting Adobe’s license server through a proxy server. </p> <p>Section identifier for parameters that enable your <span class="keyword"> client</span> to contact the Adobe License Server through a proxy server. Expand the Licensing node and complete the following parameters. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Proxy Address </p> </td> 
   <td colname="col2"> <p>Optional. The address of the proxy server that <span class="keyword"> client</span> must use to access the Adobe License Server. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Proxy Port </p> </td> 
   <td colname="col2"> <p>Optional. The port of the proxy server. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Proxy User Name </p> </td> 
   <td colname="col2"> <p>Optional. The user name for the proxy server. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Proxy Password </p> </td> 
   <td colname="col2"> <p>Optional. The password associated with the Proxy User Name. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Maximum Sample Size (MB) </p> </td> 
   <td colname="col2"> <p>Specifies the maximum size allowed in the data cache used by <span class="keyword"> the client</span> running on a single computer. </p> <p>While the Sample Bytes parameter in the <span class="filepath"> Server.cfg</span> file specifies the data cache size for all <span class="keyword"> clients</span> connecting to a Data Workbench server (250e6 bytes by default), the Maximum Sample Size parameter enables you to further limit the data cache size for a particular computer. This is useful when the client is installed on a computer with limited storage or computing power. </p> <p> <p>Note: This parameter limits the size of a local data sample queried locally by the client program. In contrast, the <span class="filepath"> cache.db</span> file contains data for each profile the client connects to, plus the element names and their dimensions. These element names and dimensions in the <span class="filepath"> cache.db</span> files are required to run local queries. Consequently, there is no way to limit its size other than reducing the number of elements in the data set. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Name </p> </td> 
   <td colname="col2">Optional. The name that <span class="keyword"> the client</span> uses to identify the <span class="keyword"> server</span>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Network Location </p> </td> 
   <td colname="col2"> <p>Optional. The network location that <span class="keyword"> client</span> uses to resolve the Data Workbench server common name to an IP address. The available network locations are defined in the address file on the server. For more information, see the <i>Server Products Installation and Administration Guide</i>. </p> <p>If you do not specify a network location, <span class="keyword"> client</span> resolves common names using the default network location, “Insight.” </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Port </p> </td> 
   <td colname="col2"> <p>The port to which <span class="keyword"> the client</span> sends requests. This port number must match the port on which the Data Workbench server is listening for requests. This is usually 443 for secure connections. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Proxy Address </p> </td> 
   <td colname="col2"> <p>If a proxy server is required to connect to your Data Workbench server computers, you must complete at least this parameter and the Proxy Port parameter. You can optionally complete the Proxy User Name and Proxy User Password parameters. </p> <p>The address of the proxy server that <span class="keyword"> the client</span> must use to access the Data Workbench server. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Proxy Password </p> </td> 
   <td colname="col2"> <p>Optional. The password to the proxy server. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Proxy Port </p> </td> 
   <td colname="col2"> <p>The port of the proxy server. The default value is 8080. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Proxy User Name </p> </td> 
   <td colname="col2"> <p>Optional. The user name for the proxy server. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Search </p> </td> 
   <td colname="col2"> <p>In the <span class="filepath"> Insight.cfg</span> (or any <span class="filepath"> .cfg</span> file), you can search by key name, key type, or value to quickly locate an entry, to remove the need to scroll through expanded, large files for nested information. You can locate dimension names, server names, and so on. </p> <p>Type a search phrase into this field to locate the data. Depending on the success of a match, the color of the field changes. Matches are shown highlighted and non-matches are dimmed. If there are no matches, the background of the search field turns red. When you press Enter, the config tree expands every place where there is a match and collapses where there is not a match. </p> <p>You can also use regular expressions in the <span class="wintitle"> Search</span> field. For example, you can use re: <span class="filepath"> *zip.*</span> for any entry containing the word “zip.” </p> <p>To clear a search, press <span class="uicontrol"> Escape</span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Servers </p> </td> 
   <td colname="col2"> <p>Vector heading for <span class="keyword"> client</span> to <span class="keyword"> server</span> connections. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>SSL Client Certificate </p> </td> 
   <td colname="col2"> <p>Optional unless you have more than one certificate. The name of the file that contains the digital certificate for this copy of Data Workbench. This is the file that you downloaded in Downloading and Installing the Digital Certificate. </p> <p>Example: <span class="filepath"> Samantha Smith.pem</span> </p> <p>If you leave this parameter blank, <span class="keyword"> the client</span> uses whatever certificate is present. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>SSL Server Common Name </p> </td> 
   <td colname="col2"> <p>The common name of the Data Workbench server (as assigned on its digital certificate). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Toolbar Icons </p> </td> 
   <td colname="col2"> <p>False turns off the icons in the workstation user interface and displays text in the toolbar. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Use Address File </p> </td> 
   <td colname="col2"> <p>Specifies whether any settings in the address file override the Address parameter setting. The options are true or false. If set to true, the settings in the address file, if present, override the Address parameter setting. The default value is true. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Use SSL </p> </td> 
   <td colname="col2">Specifies whether SSL is used for secure communication between the Data Workbench server and <span class="keyword"> the client</span>. The options are true or false. The default value is true. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Unhide All </p> </td> 
   <td colname="col2"> <p>Optional. Enables you to temporarily unhide all metrics, dimensions, and filters that have been hidden using any of the following functionality: 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">[Exclusive] setting in <span class="filepath"> order.txt</span> files </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">Hide option in <span class="filepath"> order.txt</span> files </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">Show parameter in <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span>, and <span class="filepath"> .filter</span> files. </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">Hidden parameter in the <span class="filepath"> Transformation.cfg</span> file. </li> 
     </ul> </p> <p>For more information about these methods, see <a href="../../data-workbench-client/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task_A391800A8DD444DEB3E1516D5189F999" format="dita" scope="local"> Hide a menu item</a>. </p> <p>The options are true or false. The default setting is false. Change this parameter to true to temporarily unhide hidden metrics, dimensions, and filters. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Unlock </p> </td> 
   <td colname="col2"> <p>Optional. Specifies whether you are allowed to unlock locked workspaces. The options are true and false. True enables you to unlock any locked workspace, while false does not. The default value is false. For more information about locked workspaces, see <a href="../../data-workbench-client/c-get-started/c-work-worksp/c-unlock-wksp.md#concept_18ADA952AECF45C79A806B31B294023E" format="dita" scope="local"> Unlocking a Workspace</a>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Update Software </p> </td> 
   <td colname="col2"> <p>Optional. Specifies whether to allow this <span class="keyword"> the </span>client software to be updated by the Data Workbench server. The options are true or false. The default value is true. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>User Folder </p> </td> 
   <td colname="col2"> <p>Optional. Specifies the name and location of the folder that contains the local copies of any workspaces, metrics, dimensions, or configuration files for each profile. The default setting is User\\, which specifies the User folder within the Data Workbench installation directory. </p> <p>Changing this setting is useful when two users are sharing the same computer. To accommodate both users, you can specify a shared folder to which both users have access. </p> </td> 
  </tr> 
 </tbody> 
</table>

