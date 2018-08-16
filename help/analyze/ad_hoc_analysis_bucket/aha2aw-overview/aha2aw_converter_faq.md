---
description: null
seo-description: null
seo-title: Project Converter FAQ
title: Project Converter FAQ
uuid: f45db9c2-a4c2-496d-833b-91d60a1e402c
index: y
internal: n
snippet: y
translate: y
---

# Project Converter FAQ

## Project Converter FAQ {#topic_8231595303AD403E9322645A63632D57}
>Short Description
* [ Known Conversion Issues](../../ad_hoc_analysis_bucket/aha2aw-overview/aha2aw_converter_faq.md#section_39C922A58B2E49C9877B363042801361)
* [ Conversion FAQ](../../ad_hoc_analysis_bucket/aha2aw-overview/aha2aw_converter_faq.md#section_1E53FE373AF045978F939916124E194E)

## Known Conversion Issues {#section_39C922A58B2E49C9877B363042801361}


<table id="table_C9477437CB5C492B8713237E181AFEC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Issue </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Minute granularity with breakdowns or in columns</b> </p> </td> 
   <td colname="col2"> <p>When minute granularity has breakdowns applied to it or if minute granularity is present in columns, the project cannot be converted to Analysis Workspace. </p> <p>A workaround is to remove the breakdown on minute granularity and remove it from columns, then convert the project. You can then apply breakdowns on minute granularity in Analysis Workspace. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Internal calculated metric used together with a column segment</b> </p> </td> 
   <td colname="col2"> <p>If you are using an internal calculated metric together with a column segment, the project cannot be converted to Analysis Workspace. To work around this issue, remove the internal calculated metrics from the project before conversion, then re-add them in Analysis Workspace. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Conversion FAQ {#section_1E53FE373AF045978F939916124E194E}


<table id="table_48CC119236C94835A6A512E989BE4200"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: Are any Ad Hoc Analysis features not supported in Analysis Workspace?</b> </p> </td> 
   <td colname="col2"> <p>A: The Site Analysis report is not supported in Analysis Workspace. There are also some slight differences between other visualizations in Ad Hoc Analysis and Workspace. See the questions below for more detail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How are table settings converted?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_A645A004FB094A1593439A6607FE9A6B"> 
     <li id="li_033CA771F08A4BC3B0BC52CDCCA03FF4"><b>Number of rows shown</b>: Workspace is paginated to show only 10 rows (customizable to show up to 400 rows at a time), whereas Ad Hoc will show up to 50,000 rows in a page. Note that the data is still in Workspace, just paginated to a default of 10 rows. </li> 
     <li id="li_A8B8890149334032A56D8D1C0F8691EA"><b>Advanced Search: </b>Multiple simultaneous search options are not supported, but a single search option (such as <span class="wintitle"> All of these words</span>, <span class="wintitle"> The exact phrase</span>, <span class="wintitle"> Any of these words</span>, or <span class="wintitle"> None of these words</span>) will be converted to Analysis Workspace. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How are charts/graphs converted?</b> </p> </td> 
   <td colname="col2"> <p>A: Note that charts and graphs are called "visualizations" in Workspace. </p> 
    <ul id="ul_597F5AB826EF434295D0CABD0313CAD5"> 
     <li id="li_AFB2805418034721A9519D999128C0A8"><b>Settings</b>: Visualization settings like "Number of Items" or "Number of bars" are not supported in Workspace. </li> 
     <li id="li_D5C7EA8815344EDB8585CBB8E1AF583E"><b>Pie chart</b>: Exported as a <a href="https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/donut.html" format="html" scope="external"> Donut</a> visualization. This visualization in Workspace is capped at 19 sections. </li> 
     <li id="li_91659FBFD77C4B3393D78447D658B7B4"><b>Bubble chart</b>: Exported as a <a href="https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/scatterplot.html" format="html" scope="external"> Scatterplot</a> visualization. By default, the scatterplot draws the first metric on the x-axis and the second metric on the y-axis. If there is only one metric, bubble charts will be converted to Line visualizations. </li> 
     <li id="li_FA05085FFB1747EBAF63616AC2B8D59C"><b>Histogram</b>: Supports a different bucketing logic in Workspace vs. Ad Hoc Analysis. Therefore, it is converted to a <a href="https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/bar.html" format="html" scope="external"> Bar</a> visualization. </li> 
     <li id="li_959499D20796459CA0F6BBC8F0A8D808"><b>Scatter Plot</b>: In exported projects in Analysis Workspace, the Y-axis is set as the first column, the X-axis is the second column, and diameter is the third column. </li> 
     <li id="li_14E06D7A5106405A89A07B44FFD9A92D"><b>Fallout tables</b>: To show fallthrough or fallout tables, right-click on the checkpoint and select a breakdown option. </li> 
     <li id="li_240F43C386F04111A7632A8FCA37832C"><b>Fallout report-level date ranges</b>: Customized report date ranges have not been applied to Fallout visualizations. </li> 
     <li id="li_1FF5B3FD9E424E7190AF03FD4DD9D654"><b>Flow report</b>: Flow will be moved to a separate panel to preserve date ranges &amp; segmentation. </li> 
     <li id="li_BE8F8F6EC2EA49E18EF52539BC1700E0"><b>Conversion Funnel</b>: Will be converted to a freeform table because it is not supported in Analysis Workspace. The Fallout visualization is a recommended replacement for the Conversion Funnel, but it will behave in a slightly different manner. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How are segments converted?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_15D5B17461E2402DB07DF8B0A10AAC37"> 
     <li id="li_CF9C3D235A664B15B21D9F89DC5EF7D3">Segments are internal to the converted project (not public). You can choose to make them public, as shown here: <p style="text-align: center;"><img placement="inline" href="assets/internal_segment.png" id="image_5942392F18E845A5B41C3DED59374E89" width="300px" /> </p> </li> 
     <li id="li_AE61DAEC5C0047349DD192EFEEDB0BF9">Ad Hoc Analysis workspace-level segments are applied at the project/workspace level in Workspace. </li> 
     <li id="li_B1559E2C18724FE189AF87D0BEF16811">Ad Hoc Analysis report-level segments are applied at the table column level in Workspace. </li> 
     <li id="li_0E6DF6D44EA448A4A212BA2BB8E342CF">Ad Hoc Analysis table segments are applied at the column level in Workspace. </li> 
    </ul> <p>You can edit segments in the <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/" format="https" scope="external"> Segment Builder</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How are date ranges converted?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_A24AB597F3CE4847AF00D49A9A72A395"> 
     <li id="li_24FD18AF64114445939C4FBC03F2D406">‘Last X day’ date ranges in Ad Hoc Analysis <i>exclude</i> today, while Analysis Workspace <i>includes</i> today. As such, date ranges like ‘last 90 days’ might not match exactly between tools. Use custom date ranges to retrieve the same time period in Analysis Workspace. </li> 
     <li id="li_AA4390470C494748B4B12030B1226720">Ad Hoc Analysis workspace-level date range are applied at the project/workspace level in Workspace. </li> 
     <li id="li_B8F0CDD413154856A315D087FEC4D418">Ad Hoc Analysis report-level date range are applied at the table column level in Workspace. </li> 
    </ul> <p>You can edit your custom date ranges under <span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol"> Components</span> &gt; <span class="uicontrol"> Date Ranges</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How are calculated metrics converted?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_ADA380D5D09B4223AAE4853D4C64F679"> 
     <li id="li_010572F793F54680ABE64117DAB7E800">Calculated metrics are internal to the exported project (not public). You can choose to make them public, by right-clicking the metric and clicking <span class="uicontrol"> Make Public</span>. <p style="text-align: center;"><img placement="inline" href="assets/calc_metric_internal.png" id="image_EA19BA55B161499CBDB9275A5C94BA90" width="200px" /> </p> </li> 
     <li id="li_930546EC8FEB432C8810FAF93556FC9A">All types of calculated metrics are supported for export. </li> 
     <li id="li_DFF7C6F8BB2344928D49194DA0F6EC38"><b>Allocation types</b>: Even though Analysis Workspace does not show the allocation type of a calculated metric explicitly, the export creates and matches the allocation type that was present in Ad Hoc Analysis. </li> 
    </ul> <p>You can edit the allocation type in the <a href="https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/" format="https" scope="external"> Calculated Metric Builder</a> by clicking the edit (pencil) icon. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How are Global Data Settings in Ad Hoc applied to converted projects?</b> </p> </td> 
   <td colname="col2"> <p>Global Data Settings could cause the same project exported twice to behave differently: </p> 
    <ul id="ul_E3827883DD8045FAAB359D7E85E3EEFA"> 
     <li id="li_1056CA4813C44638BEB070228AE6914C"><b>Count Repeat Instances.</b> Whatever setting was applied at the time of export is applied to the exported project in Analysis Workspace. </li> 
     <li id="li_D5405E2862CF434CA82AA9DE000F4BBC"><b>Data Sources.</b> In Analysis Workspace, all Analytics data is shown, including data sources. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: If my Ad Hoc Analysis project is scheduled, will the schedule be converted to Analysis Workspace?</b> </p> </td> 
   <td colname="col2"> <p>No, schedules are not converted. In Analysis Workspace, open the project you would like to schedule and go to <span class="uicontrol"> Share</span> &gt; <span class="uicontrol"> Send File on Schedule</span> to set up a new schedule. Be sure to cancel your scheduled project in Ad Hoc Analysis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Are there any naming differences between the two tools?</b> </p> </td> 
   <td colname="col2"> <p>A: Yes. See <a href="https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/adhocanalysis_vs_analysisworkspace.html" format="html" scope="external"> Comparison of Key Terminology </a>in the Analysis Workspace documentation. </p> </td> 
  </tr> 
 </tbody> 
</table>

