---
description: Not all segments created in the Segment Builder are compatible with Data Warehouse. This table lists the supported functions.
seo-description: Not all segments created in the Segment Builder are compatible with Data Warehouse. This table lists the supported functions.
seo-title: Data Warehouse Segment Compatibility
solution: Analytics
title: Data Warehouse Segment Compatibility
topic: Segments
uuid: e986ab09-186c-46d2-93e9-79360f00c823
index: y
internal: n
snippet: y
translate: y
---

# Data Warehouse Segment Compatibility



<table id="table_BBB1DAFDF85041598FA4AF869172CF7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Analysis Workspace, Reports &amp;amp; Analytics, Ad Hoc Analysis </th> 
   <th colname="col3" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Excludes</b> </td> 
   <td colname="col2"> Supported at any level </td> 
   <td colname="col3"> Supported only in special cases at the top level </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sequential segments</b> </td> 
   <td colname="col2"> Supported </td> 
   <td colname="col3"> Not supported </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>AND and OR can be combined without limits</b> </td> 
   <td colname="col2"> Supported </td> 
   <td colname="col3"> Some limitations </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nested containers</b> </td> 
   <td colname="col2"> Supported </td> 
   <td colname="col3"> Some limitations (they must decrease in scope, for example visitors can contain hits, but not the other way around) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensions</b> </td> 
   <td colname="col2"> Drag and drop a dimension into the Segment Builder's <span class="uicontrol"> Definitions </span> field to find out about its product compatibility. For example, these dimensions are supported only in Reports &amp; Analytics and Ad Hoc Analysis: 
    <ul id="ul_BD708CC3A16743F49F998D1046EC70A3"> 
     <li id="li_240DA619D50B4336ACD9117BF59AF10A">Entry Server </li> 
     <li id="li_222D4D4116674EF8A52945CCB9C78719">Entry Category </li> 
     <li id="li_5A43C846E2EA4EFCB892DE9E0607C68C">Entry Date </li> 
     <li id="li_8E9CABBE04FC4A7A9A5D2BDD34AD3C87">All Search Page Rank </li> 
    </ul> </td> 
   <td colname="col3"> Drag and drop a dimension into the Segment Builder's <span class="uicontrol"> Definitions </span> field to find out about its product compatibility. For example, these dimensions are supported only in Data Warehouse: 
    <ul id="ul_61A5B314CCCF497DB0385324E3309E22"> 
     <li id="li_1254089BDFAE4E0F8E51CB1511BBBF53">IP address </li> 
     <li id="li_D8E040F77A8C46A084547F4FE685CB10">Page URL </li> 
     <li id="li_4C79AE900CF6458780C124143DC6FA5B">Visitor ID </li> 
     <li id="li_4EC10645DE9740609D8DDFD4F668FE67">Experience Cloud Visitor ID </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segment stacking</b> </td> 
   <td colname="col2"> Supported </td> 
   <td colname="col3"> Not supported </td> 
  </tr> 
 </tbody> 
</table>

