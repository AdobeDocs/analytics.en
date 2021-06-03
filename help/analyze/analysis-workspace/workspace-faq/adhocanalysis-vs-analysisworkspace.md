---
description: Compares Ad Hoc Analysis terminology and tasks to Analysis Workspace.
title: Analysis Workspace compared to Ad Hoc Analysis
uuid: e4b3e40f-2b08-49a0-95f1-384d85c1640d
---

# Analysis Workspace compared to Ad Hoc Analysis

>[!IMPORTANT]
>
>Adobe is moving Ad Hoc Analysis to end of life on March 1, 2021. [Learn more](https://adobe.ly/discoverworkspace)

Compares Ad Hoc Analysis terminology and tasks to Analysis Workspace.

Analysis Workspace brings much of the Ad Hoc Analysis functionality into the browser workflow. While some terminology and features remain the same between the products, there are some new terms and approaches to analysis that are introduced in Analysis Workspace.

For a technical comparison of key features and system requirements between these two products, go [here](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/analytics-product-comparison.html).

## Comparison of Key Terminology {#section_6109406B83B043A18E46D38F130B1D2E}

| Ad Hoc Analysis | Analysis Workspace |
|--- |--- |
| Project | Workspace or Project |
| Workspace | Panel |
| Report | Freeform Table |
| Chart/Graph | Visualization|
| Hierarchy: Project > Workspaces > Reports | Hierarchy: Project > Panels > Tables |
| Ranked, Trended, Totals Report templates | Freeform Table visualization |
| Flow template | Flow visualization |
| Fallout | Fallout visualization |

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
   <td colname="col2"> <p>You can bring in dimensional items or segments as column headers to easily create comparative views of metrics. <a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/metrics/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace.html"  > Video: Adding Dimensions and Metrics to your Project in Analysis Workspace</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apply segments </p> </td> 
   <td colname="col2"> <p>Segments are available under the Segment component menu, and can be applied in 3 places in Analysis Workspace: </p> 
    <ol id="ol_800D81FE2C84459B94B085C51E140330"> 
     <li id="li_F2E050902F9A4831BBA57F466E07DEAE">At the <b>panel level</b>, which applies to many visualizations in the panel. This is similar to applying a segment to a Workspace in Ad Hoc. </li> 
     <li id="li_2D88E43E0161485C95B08DC3C593EFD9">As <b>rows in a table</b>. This is similar to adding segments to the Table Builder 'Rows/Breakdowns' section in Ad Hoc. </li> 
     <li id="li_102E1A1DAA9247C08FC46C5AB3D78113">As <b>columns of a table</b>. This is similar to adding segments to the Table Builder 'Columns' section in Ad Hoc Analysis, or applying a segment at the report level in Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/applying-segments-to-your-analysis-workspace-project.html"  > Video: Using Segments in Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/panel-level-segments.html"  > Video: Applying Segments to a Panel</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Create temporary ("ad-hoc") segments </p> </td> 
   <td colname="col2"> <p>You can <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > create instant, temporary ("ad-hoc") segments</a> in Analysis Workspace by dragging dimension items into the segment drop zone at the top of the panel. Additionally, Dropdown filters can be added in the panel drop zone to create many temporary segments at once, enabling controlled project interactions. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/ad-hoc-temporary-segments.html"  > Video: Ad-Hoc Segments in Analysis Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-drop-down-filters.html"  > Video: Dropdown filters in Analysis Workspace</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Choose Date Ranges &amp; Granularities </p> </td> 
   <td colname="col2"> <p>Date ranges &amp; granularities are available under the Time component menu, and can be used in 3 ways: </p> 
    <ol id="ol_8B57C8A840694A879B22B809C58E7482"> 
     <li id="li_58FAE6A87B494A5C9007CD35BB101608">Date ranges can be applied to columns/rows and override the panel date range selected. This is similar to Report level date ranges. </li> 
     <li id="li_85BB89EFF9C8466A992815BB7804EA37">'Apply' applies a date range to all visualizations within a panel. This is similar to a Workspace date range in Ad Hoc Analysis. </li> 
     <li id="li_BC18564A8FBB48F4A522BCAC60838759">'Apply To All Panels' applies a date range to all panels within a Workspace project. This is similar to a Project date range in Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html"  > Video: Working with Dates in Analysis Workspace</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/creating-custom-date-ranges-in-analysis-workspace.html"  > Video: Custom date ranges</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use Fallout &amp; Conversion Funnels </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md"  > Fallout visualizations</a> are available in Analysis Workspace under the Visualization component menu. Similar to Ad Hoc Analysis: </p> 
    <ol id="ol_625FF45AED4E403DBEE1A906282E8531"> 
     <li id="li_7B6C5F2682774641B82D2021786AE5C4">Fallout can span a visit or visitor, and "All visits" can optionally be included. Fallout can be quickly trended through the right-click menu. </li> 
     <li id="li_CFBDDAB8E96A445DB0624640AEB25994">Dimensional items can be connected by an OR operator (similar to groups) and events can be used in the funnel. </li> 
     <li id="li_6638E6A62C744A27B2C066E5F9EC62C0">Fallthrough and Fallout next steps can also be rendered through the right-click menu. </li> 
    </ol> <p>Additionally, Fallout in Analysis Workspace allows for <a href="/help/analyze/analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md"  > mixed dimensions</a> within steps, an improvement over Ad Hoc Analysis. Mixed dimensions within steps are handled with an AND operator. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/fallout-visualization.html"  > Video: Fallout visualization</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/multi-dimensional-fallout.html"  > Video: Using Multiple Fallout Dimensions</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/comparing-segments-in-fallout.html"  > Video: Comparing Segments in Fallout</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Examine Flow (Pathing) </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  > Flow visualizations</a> are available in Analysis Workspace under the Visualization component menu. Similar to Ad Hoc Analysis: </p> 
    <ul id="ul_42D259310823496499F7D1474E1639AF"> 
     <li id="li_5DE6980EF66A49E58B8946A0422BC02C">Flow can span a visit or visitor. </li> 
     <li id="li_70A692266D32416BA3D70C1F8999F837">Key statistics are shown in terms of % path views. </li> 
    </ul> <p>Additionally, Flow allows for <a href="/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md"  > mixed dimensions</a> and the ability to right-click and create a segment, an improvement over Ad Hoc Analysis. </p> <p>Currently, Flow in Analysis Workspace <b>cannot</b> allow users to choose a success event. </li> 
    </ul> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization.html"  > Video: Overview of Flow Visualization</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/text-wrapping-and-multi-dimensional-flow.html"  > Video: Multi-Dimensional Flow</a> </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/expanding-on-flow-visualization.html"  > Video: Creating Segments from Flow</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Perform infinite breakdowns </p> </td> 
   <td colname="col2"> <p>Analysis Workspace lets you drill down to infinite levels within the browser. Segments &amp; dimensions can be mixed. Multiple dimension items can be broken down at once by multi-selecting and then dragging on a breakdown dimension </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/dimension-breakdown-by-position.html"  > Video: Improved Breakdowns</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quickly trend data </p> </td> 
   <td colname="col2"> <p>Data can be quickly visualized by clicking the graph icon within the report row. Additionally, these quick visualizations will be linked to the source table so that you can click from one value to the next in the table and see the graph update automatically. </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/dimension-graph-live-linking.html"  > Video: Dimension-Graph Live Linking</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Select Report Suites </p> </td> 
   <td colname="col2"> <p>Multiple report suites can be added to a single project in Analysis Workspace.  </p> <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/multiple-report-suites-in-analysis-workspace.html"  > Video: Multiple Report Suites in Workspace</a> </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribution IQ </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/attribution/overview.md"  > Attribution IQ</a> in Analysis Workspace lets you add many new types of attribution models to Freeform Tables, Visualizations, and Calculated metrics. It includes 10+ rule-based and algorithmic models. </p>  <p><a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-attribution-iq-in-freeform-tables.html"  > Video: Attribution IQ in Freeform Tables</a> </p> </td> 
  </tr>  
 </tbody> 
</table>

