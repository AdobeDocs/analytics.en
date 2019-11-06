---
description: Descriptions of the fields and options in the Library Management settings in Dynamic Tag Management.
keywords: library management;page code;load library at;managed by adobe;custom;code hosted;s_code hosted
seo-description: Descriptions of the fields and options in the Library Management settings in Dynamic Tag Management.
seo-title: Library management
solution: Experience Cloud,Dynamic Tag Management
title: Library management
uuid: 4cfa47f9-ae98-4feb-a58d-a3a6e45f8d5b
---

# Library management

Descriptions of the fields and options in the Library Management settings in Dynamic Tag Management.

 **[!UICONTROL  *`Property`*]** > ![](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL Library Management]**

> [!NOTE] If more than one Adobe Analytics tool is used in a single web property, each tool must have a unique tracker variable name. Duplicative object variable names between Adobe Analytics tools within a single web property will cause conflicts.

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Page code is already present </p> </td> 
   <td colname="col2"> <p> Prevents Dynamic Tag Management from installing <span class="keyword"> Adobe Analytics</span> page code if the code is already present on your site. </p> <p>This feature allows you to use Dynamic Tag Management to add to your existing implementation rather than starting from scratch. Be sure to properly set your tracker variable name when checking this box. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Load library at &lt;<span class="term"> Page Top</span> or <span class="term"> Page Bottom</span>&gt; </p> </td> 
   <td colname="col2"> <p>Specifies where and when to load the page code. Regardless of your selection, any rules using the Analytics tool will need to have the same setting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Managed by Adobe (Recommended) </p> </td> 
   <td colname="col2"> <p>Enable Dynamic Tag Management to manage your library. </p> <p>If you select this option, the following option becomes available: </p> <p> <b>Library Version: </b>Select the latest version from the <span class="wintitle"> Library Version</span> menu. Dynamic tag management notifies you when new versions are available. You can revert to a previous version as necessary. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Custom </p> </td> 
   <td colname="col2"> <p>You can configure the library code. </p> <p>If you select this option, the following options become available: </p> <p> <b>Set report suites using custom code below: </b>When this box is checked, Dynamic Tag Management looks for a variable in your custom code called <span class="varname"> s_account</span>. This variable should contain a comma-separated list of the report suites to which you want to send data. </p> <p> <b>Code Hosted: </b>Choose an option to host the <span class="filepath"> s_code</span>: </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>In DTM</b>: You can host the <span class="filepath"> s_code</span> within Dynamic Tag Management. Click <span class="uicontrol"> Edit Code</span> to cut and paste the file directly into the editor. </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL</b>: If you have a good <span class="filepath"> s_code</span> file and are happy with the process of updating it, you can provide the URL to the file here. Dynamic tag management then consumes that <span class="filepath"> s_code</span> file for its implementation of <span class="keyword"> Adobe Analytics</span>. </li> 
    </ul> <p> <b>Open Editor: </b>Lets you <a href="/help/implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md"  > insert core AppMeasurement code</a>. This code is populated automatically when using the automatic configuration method described in <a href="/help/implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md"  > Adobe Analytics Settings</a>. </p> <p> <b>Tracker Variable Name: </b>If you want to run two instances of <span class="keyword"> Adobe Analytics</span> in parallel (one within Dynamic Tag Management and one natively), you can rename the main <span class="term"> s</span> object. Renaming the object name avoids collisions. </p> </td> 
  </tr> 
 </tbody> 
</table>

