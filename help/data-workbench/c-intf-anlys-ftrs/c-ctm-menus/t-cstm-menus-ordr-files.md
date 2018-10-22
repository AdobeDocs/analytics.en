---
description: You can customize the appearance of any menu by editing the order.txt file associated with that menu.
seo-description: You can customize the appearance of any menu by editing the order.txt file associated with that menu.
seo-title: Customize a menu using order.txt files
solution: Analytics
title: Customize a menu using order.txt files
topic: Data workbench
uuid: 63c7555a-6606-4fca-9fa6-d94d199381f7
index: y
internal: n
snippet: y
---

# Customize a menu using order.txt files

You can customize the appearance of any menu by editing the order.txt file associated with that menu.

The steps in this section apply to all types of menus.

**To edit the order.txt file to customize a menu** 

1. In the [!UICONTROL Profile Manager], in the *profile name* column, right-click the check mark for the [!DNL order.txt] file and click **[!UICONTROL Make Local]**.
1. Right-click the check mark for the [!DNL order.txt] file in the [!UICONTROL User] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL order.txt] file displays.

   ![Step Info](assets/cfg_ordertxt.png)

1. (Optional) Add or change the [Inclusive] or [Exclusive] setting at the top of the file if desired. This setting controls whether items not listed in the [!DNL order.txt] file but present in the [!UICONTROL Profile Manager] is listed on the menu. The options include:

    * **[Inclusive]:** This is the default setting. This setting results in menu items that are not specified in the [!DNL order.txt]file being listed at the bottom of the menu in alphabetical order. For example, if the [!UICONTROL Profile Manager] contained a Profile item in addition the those listed in the [!DNL order.txt] above, Profile would display below Data. 
    
    * **[Exclusive]:** This setting results in menu items that are not specified in the [!DNL order.txt] file being excluded from the menu. For example, if the [!UICONTROL Profile Manager] contained a Profile item in addition the those listed in the [!DNL order.txt] above, Profile would not be displayed anywhere on the menu. 
    
    * **blank:** If neither [Inclusive] or [Exclusive] appears at the top of the file, Data Workbench displays the menu items as if the setting were [Inclusive].

1. Complete one or more of the following steps:

    <table id="table_C5D5313DF5E4470499B0B285BA2690F0"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> To perform this task... </th> 
   <th colname="col2" class="entry"> Do the following... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Reorder menu items </p> </td> 
   <td colname="col2"> <p>Type the item names in the order that you want them to appear in Data Workbench. </p> <p>For example, as long as each menu item name matches its corresponding file or folder name, the following would result in<b> Add Table</b> appearing first, then <b>Add Visualization</b>, <b>Add Legend</b>, and <b>Add Note</b> appearing last. </p> <p><b>Add Table </b> </p> <p><b>Add Visualization </b> </p> <p><b>Add Legend </b> </p> <p><b>Add Note </b> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Rename a menu item </p> </td> 
   <td colname="col2"> <p>Rename the corresponding file or folder in the <span class="wintitle"> Profile Manager</span>, then change the name of the item in the <span class="filepath"> order.txt</span> file. </p> <p>For example, to rename Add Annotation to New Annotation, rename the Add Annotation folder in the <span class="wintitle"> Profile Manager</span> to New Annotation, then change the name of the Add Annotation item in the <span class="filepath"> order.txt</span> file to New Annotation. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Hide a menu item </p> </td> 
   <td colname="col2"> <p>To hide the menu item but not delete the item itself, type a minus sign (-) at the beginning of its name. </p> <p>For example, the following results in <span class="wintitle"> Add Annotation</span> not appearing in the menu. </p> <p>Add Legend </p> <p>-Add Annotation </p> <p>To again show the hidden menu item, simply remove the minus sign (-) or use the Unhide All parameter in the <span class="filepath"> Insight.cfg</span> file, see <a href="../../c-insght-config-param.md#concept_14DA97D0756348E885C08CA9E866074B" format="dita" scope="local"> Insight Configuration Parameters</a>. </p> <p>You can also hide menu items using the following methods: 
     <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
      <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>The Show parameter in a <span class="filepath"> .filter</span>, <span class="filepath"> .metric</span>, or <span class="filepath"> .dim</span> file hides filters, derived metrics and dimensions, and extended dimensions from their respective menus. When using this option, the item is not listed in the menu, but it is still in the profile and available to be used. </p> <p>To use this parameter to hide filters and derived metrics and dimensions, add the following line to the end of the <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span>, or <span class="filepath"> .filter</span> file: </p> <p><span class="filepath"> show = bool: false</span> </p> <p>To use this parameter to hide extended dimensions, see Chapter 10 of the <i>Dataset Configuration Guide</i> for instructions. </p> <p>You can temporarily unhide items hidden using this method by setting the Unhide All parameter in the <span class="filepath"> Insight.cfg</span> file. For more information about this parameter, see <a href="../../c-insght-config-param.md#concept_14DA97D0756348E885C08CA9E866074B" format="dita" scope="local"> Insight Configuration Parameters</a>. </p> </li> 
      <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">The Hidden parameter in the <span class="filepath"> Transformation.cfg</span> file or any dataset include file hides extended dimensions from the dimension menu. When using this option, the item is not listed in the menu, but it is still in the profile and available to be used. <p> <p>Note:  When hiding extended dimensions using this method, you must retransform your dataset for the dimensions to be hidden. </p> </p> <p>You can temporarily unhide items hidden using this method by setting the Unhide All parameter in the <span class="filepath"> Insight.cfg</span> file. For more information about this parameter, see <a href="../../c-insght-config-param.md#concept_14DA97D0756348E885C08CA9E866074B" format="dita" scope="local"> Insight Configuration Parameters</a>. </p> </li> 
      <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>Zero-byte files hide any type of item on any menu. When using this option, an empty (zero-byte) file hides the presence of a file with the same name that contains data. <span class="keyword"> Data workbench</span> treats zero-byte files as if they do not exist. For more information, see <a href="../../c-admin-intrf/c-prof-mgr/c-empty-files.md#concept_E776FAC9E5904BED8C13B9D5EB17C491" format="dita" scope="local"> Hiding Files Using Empty (Zero-byte) Files</a>. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Delete a menu item </p> </td> 
   <td colname="col2"> <p>If this file is set to use the [Exclusive] option, you can simply delete the menu item from this file. The item itself is still in the profile, but it is not listed in the menu. </p> <p>If this file is set to use the [Inclusive] option, you must remove the menu item name from this file and either delete or zero-byte the corresponding file to remove the item from the menu. </p> <p>For information about deleting files, see <a href="../../c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task_1E29C25E6C824CC9B51CB651E835856B" format="dita" scope="local"> Deleting Files from Your Working Profile</a>. For information about zero-byte files, see <a href="../../c-admin-intrf/c-prof-mgr/c-empty-files.md#concept_E776FAC9E5904BED8C13B9D5EB17C491" format="dita" scope="local"> Hiding Files Using Empty (Zero-byte) Files</a>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Add a group header </p> </td> 
   <td colname="col2"> <p>Type three hyphens before and after the heading text that you want to appear. </p> <p>For example, the following would result in a Manage group header for a set of related menu items. </p> <p>---Manage--- </p> <p>Profile </p> <p>Dataset </p> <p style="text-align: center;"> <img href="assets/cfg_ordertxt_example.png" id="image_DB5BB8A33553499A9FC6B53C544CD4CC"> </img> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Add a line to separate sections of a menu </p> </td> 
   <td colname="col2"> <p>Type three hyphens where you want a line to appear. </p> <p>For example, the following results in a line separating Add Annotation and Add Custom. </p> <p>Add Annotation </p> <p>--- </p> <p>Add Custom </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Save and close the file.
1. (Optional) To make the changes available to all users of the working profile, right-click the white check mark for the [!DNL order.txt] file in the [!UICONTROL User] column and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*.
