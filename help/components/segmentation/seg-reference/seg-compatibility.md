---
description: Not all segments created in the Segment Builder are compatible with Data Warehouse. This table lists the supported functions.
title: Data Warehouse Segment Compatibility
feature: Segmentation
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
---
# Data Warehouse Segment Compatibility

Not all segments created in the Segment Builder are compatible with [!DNL Data Warehouse]. This table lists the supported functions.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace, Reports &amp; Analytics </th> 
   <th> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td > <b>Exclude container</b> </td> 
   <td> Supported at any level </td> 
   <td> Supported only in special cases at the top level </td> 
  </tr> 
  <tr> 
   <td> <b>Sequential segments</b> </td> 
   <td> Supported </td> 
   <td> Not supported </td> 
  </tr> 
  <tr> 
   <td> <b>AND and OR can be combined without limits</b> </td> 
   <td> Supported </td> 
   <td> Some limitations. See *note* below table. </td> 
  </tr> 
  <tr> 
   <td> <b>Nested containers</b> </td> 
   <td> Supported </td> 
   <td> Some limitations (they must decrease in scope, for example visitors can contain hits, but not the other way around) </td> 
  </tr> 
  <tr> 
   <td> <b>Dimensions</b> </td> 
   <td>Drag and drop a dimension into the Segment Builder's <span class="uicontrol"> Definitions</span> field to find out about its product compatibility. For example, these dimensions are supported only in Analysis Workspace, Reports &amp; Analytics: 
    <ul> 
     <li>Entry Server </li> 
     <li>Entry Category </li> 
     <li>Entry Date </li> 
     <li>All Search Page Rank </li> 
    </ul> </td> 
   <td> Drag and drop a dimension into the Segment Builder's <span class="uicontrol"> Definitions</span> field to find out about its product compatibility. For example, these dimensions are supported only in Data Warehouse: 
    <ul> 
     <li>IP address </li> 
     <li>Page URL </li> 
     <li>Visitor ID </li> 
     <li>Experience Cloud Visitor ID </li> 
    </ul> <p>The following dimensions <b>cannot </b>be used in Data Warehouse segments: </p> 
    <ul> 
     <li>All Search Page Rank </li> 
     <li>AM/PM </li> 
     <li>Day of Month </li> 
     <li>Day of Week </li> 
     <li>Day of Year </li> 
     <li>Entry Business Unit </li> 
     <li>Entry (All Dimensions starting with Entry, except Entry Page) </li> 
     <li>Exit (All Dimensions starting with Exit, except Exit Link and Exit Page) </li> 
     <li>Hierarchy (All Dimensions starting with Hierarchy) </li> 
     <li>Hit Depth </li> 
     <li>Hit Type </li> 
     <li>Hour Day </li> 
     <li>Month of Year </li> 
     <li>Pages not Found </li> 
     <li>Paid Search </li> 
     <li>Quarter of Year </li> 
     <li>Return Frequency </li> 
     <li>Single Page Visits </li> 
     <li>Time Prior to Event </li> 
     <li>Time Spent on Page - Bucketed </li> 
     <li>Time Spent per Visit - Bucketed </li> 
     <li>Tracking Opt-out Reason </li> 
     <li>US States </li> 
     <li>Weekday/Weekend </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <b>Segment stacking</b> </td> 
   <td> Supported </td> 
   <td> Supported </td> 
  </tr>
  <tr>
    <td><b>'Equals any of' and 'Does not equal any of' operators</b></td>
    <td>Supported</td>
    <td>Not supported</td>
  </tr>
 </tbody> 
</table>

*Note: Data Warehouse does not support all cases of using an `exclusion` or `without` container when using `AND/OR`. When using such a combination, only those segments that can be re-written as `A AND NOT B`, (or **include this characteristic** and **exclude this characteristic**) are supported in Data Warehouse.*
