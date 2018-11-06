---
description: Not all segments created in the Segment Builder are compatible with Data Warehouse. This table lists the supported functions.
seo-description: Not all segments created in the Segment Builder are compatible with Data Warehouse. This table lists the supported functions.
seo-title: Data Warehouse Segment Compatibility
solution: Analytics
title: Data Warehouse Segment Compatibility
topic: Segments
uuid: 370258c5-8614-4434-871c-41753ed77f5c
index: y
internal: n
snippet: y
---

# Data Warehouse Segment Compatibility

Not all segments created in the Segment Builder are compatible with Data Warehouse. This table lists the supported functions.

<table id="table_BBB1DAFDF85041598FA4AF869172CF7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis </th> 
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
   <td colname="col2">Drag and drop a dimension into the Segment Builder's <span class="uicontrol"> Definitions</span> field to find out about its product compatibility. For example, these dimensions are supported only in Analysis Workspace, Reports &amp; Analytics and Ad Hoc Analysis: 
    <ul id="ul_BD708CC3A16743F49F998D1046EC70A3"> 
     <li id="li_240DA619D50B4336ACD9117BF59AF10A">Entry Server </li> 
     <li id="li_222D4D4116674EF8A52945CCB9C78719">Entry Category </li> 
     <li id="li_5A43C846E2EA4EFCB892DE9E0607C68C">Entry Date </li> 
     <li id="li_8E9CABBE04FC4A7A9A5D2BDD34AD3C87">All Search Page Rank </li> 
    </ul> </td> 
   <td colname="col3"> Drag and drop a dimension into the Segment Builder's <span class="uicontrol"> Definitions</span> field to find out about its product compatibility. For example, these dimensions are supported only in Data Warehouse: 
    <ul id="ul_61A5B314CCCF497DB0385324E3309E22"> 
     <li id="li_1254089BDFAE4E0F8E51CB1511BBBF53">IP address </li> 
     <li id="li_D8E040F77A8C46A084547F4FE685CB10">Page URL </li> 
     <li id="li_4C79AE900CF6458780C124143DC6FA5B">Visitor ID </li> 
     <li id="li_4EC10645DE9740609D8DDFD4F668FE67">Experience Cloud Visitor ID </li> 
    </ul> <p>The following dimensions <b>cannot </b>be used in Data Warehouse segments: </p> 
    <ul id="ul_FE143F6D1ABF45DAA444E1B5691C7D4F"> 
     <li id="li_E77F3CC45BA04674B857FE5AB19D56F1">All Search Page Rank </li> 
     <li id="li_95E1549C13F14BA0B32686401EE78E31">AM/PM </li> 
     <li id="li_6F1C8FC2E7674A0CA14B70B65784D896">Day of Month </li> 
     <li id="li_79D1A91D741D4CCC937D07906D71F964">Day of Week </li> 
     <li id="li_4008565353084611BD782B98D50C0611">Day of Year </li> 
     <li id="li_F87D78F125874087BFF74FAAE2BA46F5">Entry Business Unit </li> 
     <li id="li_53DA4E64C6714CFF90D164245D01C16A">Entry (All Dimensions starting with Entry, except Entry Page) </li> 
     <li id="li_7F26B0E54A4A48319F31D8FC499D1CF2">Exit (All Dimensions starting with Exit, except Exit Link and Exit Page) </li> 
     <li id="li_1877D2D8A95B43F29CAA426BF2FE4996">Hierarchy (All Dimensions starting with Hierarchy) </li> 
     <li id="li_DF0BCC63ED274ABEA1C5A28274936310">Hit Depth </li> 
     <li id="li_98BE56213E1A4FD28D4858D53C46D23E">Hit Type </li> 
     <li id="li_52ECB31657DF4180BDB9C8D21CC74313">Hour Day </li> 
     <li id="li_93716207F2614822ACB84100B35D27BC">Month of Year </li> 
     <li id="li_FFC8E1F7092C4876A7E9F2365CC234B9">Pages not Found </li> 
     <li id="li_7A070C8E0F664F5AB554555B17D0E4E6">Paid Search </li> 
     <li id="li_12228C18BF90463C8D8394FB810843D3">Quarter of Year </li> 
     <li id="li_1833B6E2011C4757A60CAA2C98B35AFA">Return Frequency </li> 
     <li id="li_39154CD74A534D9AA09C701FE1E2C521">Single Page Visits </li> 
     <li id="li_84BDE34DD577488881E8842D2DE72D3C">Time Prior to Event </li> 
     <li id="li_552BE3414CC949B3B24BE99298945874">Time Spent on Page - Bucketed </li> 
     <li id="li_33D815E04CB3493C82BE33E958C2D7B9">Time Spent per Visit - Bucketed </li> 
     <li id="li_76F2BB88B8CD456DB50D04F36BB7854B">Tracking Opt-out Reason </li> 
     <li id="li_07345E08D0584CEC99128A0542587019">US States </li> 
     <li id="li_3D6BD9E927334B9BBC29E602D1103F7A">Weekday/Weekend </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segment stacking</b> </td> 
   <td colname="col2"> Supported </td> 
   <td colname="col3"> Not supported </td> 
  </tr> 
 </tbody> 
</table>

