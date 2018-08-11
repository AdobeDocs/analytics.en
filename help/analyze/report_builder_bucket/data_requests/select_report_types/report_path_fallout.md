---
description: Describes how report builder supports pathing and fallout reports and how the implementation differs from Reports & Analytics.
seo-description: Describes how report builder supports pathing and fallout reports and how the implementation differs from Reports & Analytics.
seo-title: Path and path fallout reports in Report Builder
solution: Analytics
title: Path and path fallout reports in Report Builder
topic: Report builder
uuid: 01cb1500-72cf-41ae-90e2-0636388707c1
index: y
internal: n
snippet: y
translate: y
---

# Path and path fallout reports in Report Builder


<table id="table_0A4F5BDC7E104BC88C6479D2ACC28A60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Path Report Name in Reports &amp; Analytics <p>(Paths &gt; <span class="varname"> dimension </span> &gt;) </p> </th> 
   <th colname="col2" class="entry"> Supported in Report Builder? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Next/Previous <span class="varname"> dimension </span> Flow </td> 
   <td colname="col2"> Not provided as a standalone report. Can be reproduced with several requests with the Path dimension and using a filter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Next/Previous <span class="varname"> dimension </span> </td> 
   <td colname="col2"> Not provided as a standalone report. Can be reproduced with a Path report and using a filter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fallout </td> 
   <td colname="col2"> Supported and provided as a standalone report ( <span class="uicontrol"> Paths </span> &gt; <span class="varname"> dimension </span> &gt; <span class="varname"> dimension </span> <span class="uicontrol"> Fallout </span>). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Full Paths </td> 
   <td colname="col2"> Not supported. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PathFinder </td> 
   <td colname="col2"> Not provided as a standalone report. Can be reproduced as a Path report using a filter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Path Length </td> 
   <td colname="col2"> Supported only for the Page dimension. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page Analysis &gt; <span class="varname"> dimension </span> Summary </td> 
   <td colname="col2"> Not provided as a standalone report. Can be reproduced with several requests with the Path dimension and using a filter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page Analysis &amp;gt; Reloads </td> 
   <td colname="col2"> Not provided as a standalone report. Can be reproduced with a dimension report using the <span class="uicontrol"> Reloads </span> metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page Analysis &gt; <span class="varname"> dimension </span> Depth </td> 
   <td colname="col2"> Supported only for the Page dimension. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page Analysis &gt; Time Spent on <span class="varname"> dimension </span> </td> 
   <td colname="col2"> Not supported. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entries and Exits &amp;gt; Entry Pages </td> 
   <td colname="col2"> Not provided as a standalone report. Can be reproduced as a Path report using the pre-defined filter <span class="uicontrol"> Entered Site </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entries and Exits &amp;gt; Original Entry Pages </td> 
   <td colname="col2"> Supported only for the Page dimension. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entries and Exits &amp;gt; Single Page Visits </td> 
   <td colname="col2"> Not provided as a standalone report. Can be reproduced as a Path report using a pre-defined filter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entries and Exits &gt; Exit <span class="varname"> dimension </span> </td> 
   <td colname="col2"> Not provided as a standalone report. Can be reproduced as a Path report using the pre-defined filter <span class="uicontrol"> Exited Site </span>. </td> 
  </tr> 
 </tbody> 
</table>

