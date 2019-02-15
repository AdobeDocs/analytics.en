---
description: Compares Ad Hoc Analysis terminology and tasks to Analysis Workspace.
seo-description: Compares Ad Hoc Analysis terminology and tasks to Analysis Workspace.
seo-title: Analysis Workspace compared to Ad Hoc Analysis
title: Analysis Workspace compared to Ad Hoc Analysis
uuid: e4b3e40f-2b08-49a0-95f1-384d85c1640d
---

# Analysis Workspace compared to Ad Hoc Analysis

Compares Ad Hoc Analysis terminology and tasks to Analysis Workspace.

Analysis Workspace brings much of the Ad Hoc Analysis functionality into the browser workflow. While some terminology and features remain the same between the products, there are some new terms and approaches to analysis that are introduced in Analysis Workspace.

For a technical comparison of key features and system requirements between these two products, go [here](https://marketing.adobe.com/resources/help/en_US/reference/analytics-product-comparison.html).

## Comparison of Key Terminology {#section_6109406B83B043A18E46D38F130B1D2E}

| Ad Hoc Analysis | Analysis Workspace |
|--- |--- |
|Project|Workspace or Project|
|Workspace|Panel|
|Report|Freeform Table|
|Charts/Graph|Visualization|
|Hierarchy: Project > Workspaces > Reports|Hierarchy: Project > Panels > Tables|
|Ranked, Trended, Totals Report templates|Freeform Table visualization|
|Flow template|Flow visualization|
|Fallout|Fallout visualization|

## Comparison of Key Tasks {#section_F31446F1DFA742D794A30D713E223440}

<table id="table_90D4461F04F34D70844C5E3FBB0BBE44"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ad Hoc Analysis Task </th> 
   <th colname="col2" class="entry"> Analysis Workspace Task </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Add dimensions &amp; segments to metric columns </p> </td> 
   <td colname="col2"> <p>You can bring in dimensional items or segments as column headers to easily create comparative views of metrics. <a href="https://www.youtube.com/watch?v=P9W0hhIHhCs" format="https" scope="external"> Video: Working with Dimensions</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apply segments </p> </td> 
   <td colname="col2"> <p>Segments are available under the Segment component menu, and can be applied in 3 places in Analysis Workspace: </p> 
    <ol id="ol_800D81FE2C84459B94B085C51E140330"> 
     <li id="li_F2E050902F9A4831BBA57F466E07DEAE">At the <b>panel level</b>, which applies to many visualizations in the panel. This is similar to applying a segment to a Workspace in Ad Hoc. </li> 
     <li id="li_2D88E43E0161485C95B08DC3C593EFD9">As <b>rows in a table</b>. This is similar to adding segments to the Table Builder 'Rows/Breakdowns' section in Ad Hoc. </li> 
     <li id="li_102E1A1DAA9247C08FC46C5AB3D78113">As <b>columns of a table</b>. This is similar to adding segments to the Table Builder 'Columns' section in Ad Hoc Analysis, or applying a segment at the report level in Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://www.youtube.com/watch?v=QlUCdQDnni4" format="https" scope="external"> Video: Using Segments in Workspace</a> </p> <p><a href="https://www.youtube.com/watch?v=YjaRlJoQqRA" format="https" scope="external"> Video: Applying Segments to a Panel</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Choose Date Ranges &amp; Granularities </p> </td> 
   <td colname="col2"> <p>Date ranges &amp; granularities are available under the Time component menu, and can be used in 3 ways: </p> 
    <ol id="ol_8B57C8A840694A879B22B809C58E7482"> 
     <li id="li_58FAE6A87B494A5C9007CD35BB101608">Date ranges can be applied to columns/rows and override the panel date range selected. This is similar to Report level date ranges. </li> 
     <li id="li_85BB89EFF9C8466A992815BB7804EA37">'Apply' applies a date range to all visualizations within a panel. This is similar to a Workspace date range in Ad Hoc Analysis. </li> 
     <li id="li_BC18564A8FBB48F4A522BCAC60838759">'Apply To All Panels' applies a date range to all panels within a Workspace project. This is similar to a Project date range in Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://www.youtube.com/watch?v=ybmv6EBmhn0" format="https" scope="external"> Video: Working with Dates in Analysis Workspace</a> </p> <p><a href="https://www.youtube.com/watch?v=L4FSrxr3SDA" format="https" scope="external"> Video: Custom date ranges</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Create internal ("ad-hoc") segments </p> </td> 
   <td colname="col2"> <p>You can <a href="../../analyze/analysis-workspace/components/t-freeform-project-segment.md#task_11C6A2C7717B48049E5750B9D20FEC80" format="dita" scope="local"> create instant, internal ("ad-hoc") segments</a> in Analysis Workspace by dragging dimension items into the segment drop zone at the top of the panel. </p> <p><a href="https://www.youtube.com/watch?v=NKm7Rj23TtE" format="https" scope="external"> Video: Ad Hoc Segments in Analysis Workspace</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use Fallout &amp; Conversion Funnels </p> </td> 
   <td colname="col2"> <p><a href="../../analyze/analysis-workspace/visualizations/fallout/fallout-flow.md#concept_D7ED51D138C747CA8F35BD93F21E79A6" format="dita" scope="local"> Fallout visualizations</a> are available in Analysis Workspace under the Visualization component menu. Similar to Ad Hoc Analysis: </p> 
    <ol id="ol_625FF45AED4E403DBEE1A906282E8531"> 
     <li id="li_7B6C5F2682774641B82D2021786AE5C4">Fallout can span a visit or visitor, and "All visits" can optionally be included. Fallout can be quickly trended through the right-click menu. </li> 
     <li id="li_CFBDDAB8E96A445DB0624640AEB25994">Dimensional items can be connected by an OR operator (similar to groups) and events can be used in the funnel. </li> 
     <li id="li_6638E6A62C744A27B2C066E5F9EC62C0">Fallthrough and Fallout next steps can also be rendered through the right-click menu. </li> 
    </ol> <p>Additionally, Fallout in Analysis Workspace allows for <a href="../../analyze/analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md#concept_FBA8B0DE02DB4764AEAA0E7F52D02026" format="dita" scope="local"> mixed dimensions</a> within steps, an improvement over Ad Hoc Analysis. Mixed dimensions within steps are handled with an AND operator. </p> <p><a href="https://www.youtube.com/watch?v=VcrfHSyIoj8" format="https" scope="external"> Video: Fallout and Funnels</a> </p> <p><a href="https://www.youtube.com/watch?v=EeLV366pQag" format="https" scope="external"> Video: Using Multiple Fallout Dimensions</a> </p> <p><a href="https://www.youtube.com/watch?v=H-oT3QZlyZQ" format="https" scope="external"> Video: Comparing Segments in Fallout</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Examine Flow (Pathing) </p> </td> 
   <td colname="col2"> <p><a href="../../analyze/analysis-workspace/visualizations/c-flow/flow.md#concept_2F210EC358ED4887AE6DAA8C095DB55E" format="dita" scope="local"> Flow visualizations</a> are available in Analysis Workspace under the Visualization component menu. Similar to Ad Hoc Analysis: </p> 
    <ul id="ul_42D259310823496499F7D1474E1639AF"> 
     <li id="li_5DE6980EF66A49E58B8946A0422BC02C">Flow can span a visit or visitor. </li> 
     <li id="li_70A692266D32416BA3D70C1F8999F837">Key statistics are shown in terms of % path views. </li> 
    </ul> <p>Additionally, Flow allows for <a href="../../analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md#concept_7D1D66E9D34D4C52902C8E2D92658B27" format="dita" scope="local"> mixed dimensions</a> and the ability to right-click and create a segment, an improvement over Ad Hoc Analysis. </p> <p>Currently, Flow in Analysis Workspace <b>cannot</b>: </p> 
    <ul id="ul_2696A9DCB86E427DB5267BE2793693FF"> 
     <li id="li_384141A577BB4A94899C3E36714225EE">Turn off repeat instances. </li> 
     <li id="li_CC451BFB9FFC4C68AE28A7462B339460">Allow users to choose a success event. </li> 
    </ul> <p><a href="https://www.youtube.com/watch?v=3R1HTM7y_RM" format="https" scope="external"> Video: Overview of Flow Visualization</a> </p> <p><a href="https://www.youtube.com/watch?v=m1Wa6inC1rQ" format="https" scope="external"> Video: Multi-Dimensional Flow</a> </p> <p><a href="https://www.youtube.com/watch?v=XrJoNQy6RaQ" format="https" scope="external"> Video: Creating Segments from Flow</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Perform infinite breakdowns </p> </td> 
   <td colname="col2"> <p>Analysis Workspace lets you drill down to infinite levels within the browser. Segments &amp; dimensions can be mixed. Multiple dimension items can be broken down at once by multi-selecting and then dragging on a breakdown dimension </p> <p><a href="https://www.youtube.com/watch?v=3mQ2HN7-lIc" format="https" scope="external"> Video: Improved Breakdowns</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quickly trend data </p> </td> 
   <td colname="col2"> <p>Data can be quickly visualized by clicking the graph icon within the report row. Additionally, these quick visualizations will be linked to the source table so that you can click from one value to the next in the table and see the graph update automatically. </p> <p><a href="https://www.youtube.com/watch?v=kzlPjsBVYFQ" format="https" scope="external"> Video: Dimension-Graph Live Linking</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Select Report Suites </p> </td> 
   <td colname="col2"> <p>Similar to Ad Hoc Analysis, only one report suite can be selected for a Workspace project. Multi-report-suite handling is planned, however. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribution IQ </p> </td> 
   <td colname="col2"> <p><a href="../../analyze/analysis-workspace/attribution-iq/attribution.md#concept_5BDCF631FCC841FF920FE07F1B0D08A2" format="dita" scope="local"> Attribution IQ</a> in Analysis Workspace lets you add many new types of attribution models to Freeform Tables, Visualizations, and Calculated metrics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Not included </p> </td> 
   <td colname="col2"> <p>Add date ranges to segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Not included </p> </td> 
   <td colname="col2"> <p>Use "Only Before/Only After" sequencing in segments. </p> </td> 
  </tr> 
 </tbody> 
</table>

